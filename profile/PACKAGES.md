# Package catalog

Every Nuv Tools package published on [nuget.org](https://www.nuget.org/profiles/nuvtools), grouped
by the repository it is built from. The badge shows the latest published version.

Unless a row says otherwise, a package targets **.NET 8, 9 and 10**. All of them are MIT-licensed.

[Back to the overview](https://github.com/nuvtools)

## Foundation

### [nuvtools-common](https://github.com/nuvtools/nuvtools-common)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Common](https://www.nuget.org/packages/NuvTools.Common) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Common) | Common library for Web, Desktop and Mobile (MAUI) applications |

### [nuvtools-resources](https://github.com/nuvtools/nuvtools-resources)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Resources](https://www.nuget.org/packages/NuvTools.Resources) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Resources) | English and Portuguese localization resources: actions, fields and parameterized message templates |

### [nuvtools-validation](https://github.com/nuvtools/nuvtools-validation)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Validation](https://www.nuget.org/packages/NuvTools.Validation) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Validation) | E-mail and numeric validators, Brazilian documents (CPF, CNPJ, phone, CEP), password complexity attributes and data annotations |

## Data

### [nuvtools-data](https://github.com/nuvtools/nuvtools-data)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Data](https://www.nuget.org/packages/NuvTools.Data) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Data) | ORM-agnostic paging, sorting and filtering for `IQueryable` and `IEnumerable` |
| [NuvTools.Data.EntityFrameworkCore](https://www.nuget.org/packages/NuvTools.Data.EntityFrameworkCore) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Data.EntityFrameworkCore) | `DbContextBase` with CRUD operations, Result-pattern error handling, transactions and bulk operations |
| [NuvTools.Data.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/NuvTools.Data.EntityFrameworkCore.SqlServer) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Data.EntityFrameworkCore.SqlServer) | SQL Server registration and configuration for the package above |
| [NuvTools.Data.EntityFrameworkCore.PostgreSQL](https://www.nuget.org/packages/NuvTools.Data.EntityFrameworkCore.PostgreSQL) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Data.EntityFrameworkCore.PostgreSQL) | PostgreSQL registration and configuration for the package above |

## Web

### [nuvtools-aspnetcore](https://github.com/nuvtools/nuvtools-aspnetcore)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.AspNetCore](https://www.nuget.org/packages/NuvTools.AspNetCore) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.AspNetCore) | ASP.NET Core helpers, including composite localization |
| [NuvTools.AspNetCore.EntityFrameworkCore](https://www.nuget.org/packages/NuvTools.AspNetCore.EntityFrameworkCore) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.AspNetCore.EntityFrameworkCore) | Service base classes with CRUD operations, and database migration helpers |
| [NuvTools.AspNetCore.Blazor](https://www.nuget.org/packages/NuvTools.AspNetCore.Blazor) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.AspNetCore.Blazor) | JavaScript interop services: clipboard, local and session storage, loading indicator, file download |
| [NuvTools.AspNetCore.Blazor.MudBlazor](https://www.nuget.org/packages/NuvTools.AspNetCore.Blazor.MudBlazor) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.AspNetCore.Blazor.MudBlazor) | MudBlazor converters, validators and a server-paged table base component |

## Security

### [nuvtools-security](https://github.com/nuvtools/nuvtools-security)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Security](https://www.nuget.org/packages/NuvTools.Security) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security) | JWT handling, cryptography utilities, `ClaimsPrincipal` extensions, and the shared CAPTCHA, certificate and facial verification contracts |
| [NuvTools.Security.AspNetCore](https://www.nuget.org/packages/NuvTools.Security.AspNetCore) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.AspNetCore) | Security configuration, authenticated user services and adaptive CAPTCHA verification for ASP.NET Core |
| [NuvTools.Security.AspNetCore.Blazor](https://www.nuget.org/packages/NuvTools.Security.AspNetCore.Blazor) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.AspNetCore.Blazor) | Authentication state providers for Blazor with JWT and OIDC, and an adaptive CAPTCHA component |
| [NuvTools.Security.Biometrics.Serpro](https://www.nuget.org/packages/NuvTools.Security.Biometrics.Serpro) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.Biometrics.Serpro) | Facial verification through SERPRO Datavalid |
| [NuvTools.Security.Certificate.Lacuna](https://www.nuget.org/packages/NuvTools.Security.Certificate.Lacuna) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.Certificate.Lacuna) | ICP-Brasil certificate authentication through Lacuna REST PKI |

### [nuvtools-security-identity](https://github.com/nuvtools/nuvtools-security-identity)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Security.Identity](https://www.nuget.org/packages/NuvTools.Security.Identity) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.Identity) | Permission-based authorization with a dynamic policy provider for ASP.NET Identity |
| [NuvTools.Security.Identity.Models](https://www.nuget.org/packages/NuvTools.Security.Identity.Models) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.Identity.Models) | Base models, form DTOs and API models with localized validation, for user and role management |
| [NuvTools.Security.Identity.AspNetCore](https://www.nuget.org/packages/NuvTools.Security.Identity.AspNetCore) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.Identity.AspNetCore) | User management service: e-mail confirmation, password management and role administration |
| [NuvTools.Security.Identity.EntityFrameworkCore](https://www.nuget.org/packages/NuvTools.Security.Identity.EntityFrameworkCore) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Security.Identity.EntityFrameworkCore) | Entity Framework Core persistence for ASP.NET Identity, with transactions and batch operations |

## Integration

### [nuvtools-notification](https://github.com/nuvtools/nuvtools-notification)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Notification.Mail](https://www.nuget.org/packages/NuvTools.Notification.Mail) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Mail) | E-mail contract: `IMailService` and the message models |
| [NuvTools.Notification.Mail.Smtp](https://www.nuget.org/packages/NuvTools.Notification.Mail.Smtp) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Mail.Smtp) | SMTP provider, on MailKit and MimeKit |
| [NuvTools.Notification.Mail.Twilio](https://www.nuget.org/packages/NuvTools.Notification.Mail.Twilio) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Mail.Twilio) | Twilio Email API provider |
| [NuvTools.Notification.Messaging](https://www.nuget.org/packages/NuvTools.Notification.Messaging) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Messaging) | Messaging contract: `IMessageSender` and `IMessageConsumer` |
| [NuvTools.Notification.Messaging.Azure.ServiceBus](https://www.nuget.org/packages/NuvTools.Notification.Messaging.Azure.ServiceBus) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Messaging.Azure.ServiceBus) | Azure Service Bus provider: sender and receiver |
| [NuvTools.Notification.Realtime](https://www.nuget.org/packages/NuvTools.Notification.Realtime) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Realtime) | Real-time contract for broadcasting to connected clients |
| [NuvTools.Notification.Realtime.Azure.SignalR](https://www.nuget.org/packages/NuvTools.Notification.Realtime.Azure.SignalR) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Realtime.Azure.SignalR) | Azure SignalR provider, server side |
| [NuvTools.Notification.Realtime.Azure.SignalR.Client](https://www.nuget.org/packages/NuvTools.Notification.Realtime.Azure.SignalR.Client) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Notification.Realtime.Azure.SignalR.Client) | Azure SignalR receiver for client applications, with built-in debouncing |

### [nuvtools-payment](https://github.com/nuvtools/nuvtools-payment)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Payment](https://www.nuget.org/packages/NuvTools.Payment) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Payment) | Provider-neutral contracts: customers and saved payment methods, payee accounts and onboarding, charges and transfers |
| [NuvTools.Payment.Stripe.ApiClient](https://www.nuget.org/packages/NuvTools.Payment.Stripe.ApiClient) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Payment.Stripe.ApiClient) | Stripe provider: customers, Connect Express onboarding, separate charges and transfers, webhook signatures. **.NET 10 only** |
| [NuvTools.Payment.Omie.ApiClient](https://www.nuget.org/packages/NuvTools.Payment.Omie.ApiClient) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Payment.Omie.ApiClient) | Typed HTTP client for the Omie ERP API. **.NET 10 only** |

### [nuvtools-storage](https://github.com/nuvtools/nuvtools-storage)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Storage](https://www.nuget.org/packages/NuvTools.Storage) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Storage) | File storage contract, independent of the cloud provider |
| [NuvTools.Storage.Azure](https://www.nuget.org/packages/NuvTools.Storage.Azure) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Storage.Azure) | Azure Blob Storage provider |

### [nuvtools-blockchain](https://github.com/nuvtools/nuvtools-blockchain)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Blockchain](https://www.nuget.org/packages/NuvTools.Blockchain) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Blockchain) | Contract for tamper-evident, append-only ledger operations |
| [NuvTools.Blockchain.Azure](https://www.nuget.org/packages/NuvTools.Blockchain.Azure) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Blockchain.Azure) | Azure Confidential Ledger provider |

## Reporting

### [nuvtools-report](https://github.com/nuvtools/nuvtools-report)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.Report](https://www.nuget.org/packages/NuvTools.Report) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Report) | Report model: document and table hierarchy, reflection-based data binding, and the PDF and sheet abstractions |
| [NuvTools.Report.Pdf](https://www.nuget.org/packages/NuvTools.Report.Pdf) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Report.Pdf) | PDF generation with table rendering, company branding and document merging, on QuestPDF and PDFsharp |
| [NuvTools.Report.Sheet](https://www.nuget.org/packages/NuvTools.Report.Sheet) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Report.Sheet) | Excel export with multi-sheet workbooks on ClosedXML, and CSV export and import |
| [NuvTools.Report.FixedLength](https://www.nuget.org/packages/NuvTools.Report.FixedLength) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.Report.FixedLength) | Reader for fixed-length (positional) text files, driven by attributes |

## Data Provider

### [nuvtools-dataprovider-sdk](https://github.com/nuvtools/nuvtools-dataprovider-sdk)

| Package | Version | What it is |
|---|---|---|
| [NuvTools.DataProvider.Client](https://www.nuget.org/packages/NuvTools.DataProvider.Client) | ![NuGet](https://img.shields.io/nuget/v/NuvTools.DataProvider.Client) | Consumer SDK for the Nuv Tools Data Provider marketplace: a named `HttpClient` based at an API's address, with the access token attached |
