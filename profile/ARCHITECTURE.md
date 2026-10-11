# Architecture

How the Nuv Tools packages are put together, and how they are meant to be referenced from an
application. The list of packages is in the [package catalog](https://github.com/nuvtools/.github/blob/main/profile/PACKAGES.md).

[Back to the overview](https://github.com/nuvtools)

## Contract and provider

Anything that talks to an outside service is split in two: a **contract** package that names the
operation and knows no vendor, and one **provider** package per vendor that implements it. The
vendor's SDK is referenced only by the provider.

```mermaid
flowchart LR
    app[Application code] -->|depends on| contract["Contract package<br/>interfaces and models"]
    root[Composition root] -->|registers| provider["Provider package<br/>one per vendor"]
    provider -->|implements| contract
    provider -->|calls| vendor[(Vendor service)]
```

Application code depends on the contract alone; the provider is chosen where the services are
registered. Changing vendor is then a change in one place, and the code that sends an e-mail or
stores a file does not move.

| Contract | Providers |
|---|---|
| `NuvTools.Storage` | `NuvTools.Storage.Azure` |
| `NuvTools.Notification.Mail` | `NuvTools.Notification.Mail.Smtp`, `NuvTools.Notification.Mail.Twilio` |
| `NuvTools.Notification.Messaging` | `NuvTools.Notification.Messaging.Azure.ServiceBus` |
| `NuvTools.Notification.Realtime` | `NuvTools.Notification.Realtime.Azure.SignalR` |
| `NuvTools.Blockchain` | `NuvTools.Blockchain.Azure` |
| `NuvTools.Payment` | `NuvTools.Payment.Stripe.ApiClient` |
| `NuvTools.Security` (facial verification) | `NuvTools.Security.Biometrics.Serpro` |
| `NuvTools.Security` (certificate authentication) | `NuvTools.Security.Certificate.Lacuna` |
| `NuvTools.Data.EntityFrameworkCore` | `NuvTools.Data.EntityFrameworkCore.SqlServer`, `NuvTools.Data.EntityFrameworkCore.PostgreSQL` |
| `NuvTools.Report` | `NuvTools.Report.Pdf`, `NuvTools.Report.Sheet`, `NuvTools.Report.FixedLength` |

## Dependencies between packages

Only the references that cross from one package to another are drawn; an arrow means "references".
References to `NuvTools.Common` are listed under the diagram instead of drawn, because nearly
everything has one and the arrows would bury the rest.

Packages that reference no other Nuv Tools package and are referenced by none — the notification,
storage, blockchain and report families — are left out, since within each of them the only
references are from a provider to its contract.

```mermaid
flowchart BT
    subgraph foundation[Foundation]
        Common[NuvTools.Common]
        Resources[NuvTools.Resources]
        Validation[NuvTools.Validation]
    end

    subgraph data[Data]
        Data[NuvTools.Data]
        DataEF[NuvTools.Data.EntityFrameworkCore]
        DataSql["NuvTools.Data.EntityFrameworkCore.SqlServer"]
        DataPg["NuvTools.Data.EntityFrameworkCore.PostgreSQL"]
    end

    subgraph web[Web]
        Asp[NuvTools.AspNetCore]
        AspEF[NuvTools.AspNetCore.EntityFrameworkCore]
        Blazor[NuvTools.AspNetCore.Blazor]
        Mud[NuvTools.AspNetCore.Blazor.MudBlazor]
    end

    subgraph security[Security]
        Sec[NuvTools.Security]
        SecAsp[NuvTools.Security.AspNetCore]
        SecBlazor[NuvTools.Security.AspNetCore.Blazor]
        Serpro[NuvTools.Security.Biometrics.Serpro]
        Lacuna[NuvTools.Security.Certificate.Lacuna]
    end

    subgraph identity[Security.Identity]
        Id[NuvTools.Security.Identity]
        IdModels[NuvTools.Security.Identity.Models]
        IdAsp[NuvTools.Security.Identity.AspNetCore]
        IdEF[NuvTools.Security.Identity.EntityFrameworkCore]
    end

    subgraph payment[Payment]
        Pay[NuvTools.Payment]
        Stripe[NuvTools.Payment.Stripe.ApiClient]
        Omie[NuvTools.Payment.Omie.ApiClient]
    end

    DataEF --> Data
    DataSql --> DataEF
    DataPg --> DataEF

    AspEF --> Asp
    AspEF --> DataEF
    Mud --> Blazor
    Mud --> Data

    SecAsp --> Sec
    SecBlazor --> Sec
    SecBlazor --> Blazor
    Serpro --> Sec
    Serpro --> Validation
    Lacuna --> Sec

    Id --> Sec
    IdModels --> Resources
    IdModels --> Validation
    IdAsp --> Sec
    IdAsp --> IdModels
    IdEF --> DataEF

    Stripe --> Pay
```

**Reference `NuvTools.Common`:** `NuvTools.Data.EntityFrameworkCore`,
`NuvTools.AspNetCore.Blazor.MudBlazor`, `NuvTools.Security.AspNetCore`,
`NuvTools.Security.AspNetCore.Blazor`, `NuvTools.Security.Biometrics.Serpro`,
`NuvTools.Security.Certificate.Lacuna`, `NuvTools.Security.Identity.AspNetCore`, `NuvTools.Payment`,
`NuvTools.Payment.Stripe.ApiClient`, `NuvTools.Payment.Omie.ApiClient` and, in its own repository,
`NuvTools.DataProvider.Client`, which references nothing else.

## Where each package belongs in an application

The packages are layered the way a typical layered or clean-architecture solution is, so each one
has an obvious home. A contract is referenced from the application layer; its provider is referenced
only where services are registered.

```mermaid
flowchart TB
    subgraph presentation[Presentation]
        api["ASP.NET Core API<br/>NuvTools.AspNetCore<br/>NuvTools.Security.AspNetCore"]
        ui["Blazor UI<br/>NuvTools.AspNetCore.Blazor<br/>NuvTools.Security.AspNetCore.Blazor"]
    end

    subgraph application[Application]
        app["Use cases<br/>NuvTools.Common, NuvTools.Validation, NuvTools.Resources<br/>Contracts: Storage, Notification, Payment, Blockchain, Report"]
    end

    subgraph infrastructure[Infrastructure]
        persistence["Persistence<br/>NuvTools.Data.EntityFrameworkCore<br/>SqlServer or PostgreSQL"]
        providers["Providers<br/>Storage.Azure, Mail.Smtp, Messaging.Azure.ServiceBus,<br/>Payment.Stripe.ApiClient, Report.Pdf and the others"]
    end

    api --> app
    ui --> api
    persistence --> app
    providers --> app
```

## Versioning and targets

- The current package versions are in the **10.x** line.
- Each package is versioned on its own; two packages from the same repository can carry different
  version numbers.
- The packages target **.NET 8, 9 and 10**, except `NuvTools.Payment.Stripe.ApiClient` and
  `NuvTools.Payment.Omie.ApiClient`, which target .NET 10 only.
