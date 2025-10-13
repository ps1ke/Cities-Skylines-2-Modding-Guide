# PDX.SDK.Contracts.Service.Account.IAccountService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Account`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IAccountService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.CreateResult> Create(PDX.SDK.Contracts.Credential.EmailAndPasswordCredential emailAndPassword, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.CreateResult> Create(PDX.SDK.Contracts.Credential.EmailAndPasswordCredential emailAndPassword, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth, System.String source, System.String referer, System.String sourceService, System.String campaign, System.String medium, System.String channel, System.String firstName, System.String lastName, System.String addressLine1, System.String addressLine2, System.String city, System.String state, System.String zipCode, System.String emailTemplate, System.String landingUrl, System.String refererAccount, System.Boolean marketingPermission);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.ExistsResult> Exists(PDX.SDK.Contracts.Credential.ICredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.GetDetailsResult> GetDetails();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.LoginResult> Login(PDX.SDK.Contracts.Credential.ICredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Logout();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> ReportPlayer(System.String reportedAccountId, System.String category);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> ResetPassword(System.String email);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.StartupResult> Startup();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UpdateDetails(System.Nullable<PDX.SDK.Contracts.Enums.Language> language, System.Nullable<PDX.SDK.Contracts.Enums.Country> country, System.Nullable<System.DateTime> dateOfBirth, System.String firstName, System.String lastName, System.String addressLine1, System.String addressLine2, System.String city, System.String state, System.String zipCode);
}
```


## Methods

- `public abstract Create(PDX.SDK.Contracts.Credential.EmailAndPasswordCredential emailAndPassword, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.CreateResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.CreateResult> Create(PDX.SDK.Contracts.Credential.EmailAndPasswordCredential emailAndPassword, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth);
```

- `public abstract Create(PDX.SDK.Contracts.Credential.EmailAndPasswordCredential emailAndPassword, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth, System.String source = null, System.String referer = null, System.String sourceService = null, System.String campaign = null, System.String medium = null, System.String channel = null, System.String firstName = null, System.String lastName = null, System.String addressLine1 = null, System.String addressLine2 = null, System.String city = null, System.String state = null, System.String zipCode = null, System.String emailTemplate = null, System.String landingUrl = null, System.String refererAccount = null, System.Boolean marketingPermission = False) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.CreateResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.CreateResult> Create(PDX.SDK.Contracts.Credential.EmailAndPasswordCredential emailAndPassword, PDX.SDK.Contracts.Enums.Language language, PDX.SDK.Contracts.Enums.Country country, System.DateTime dateOfBirth, System.String source, System.String referer, System.String sourceService, System.String campaign, System.String medium, System.String channel, System.String firstName, System.String lastName, System.String addressLine1, System.String addressLine2, System.String city, System.String state, System.String zipCode, System.String emailTemplate, System.String landingUrl, System.String refererAccount, System.Boolean marketingPermission);
```

- `public abstract Exists(PDX.SDK.Contracts.Credential.ICredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.ExistsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.ExistsResult> Exists(PDX.SDK.Contracts.Credential.ICredential credential);
```

- `public abstract GetDetails() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.GetDetailsResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.GetDetailsResult> GetDetails();
```

- `public abstract Login(PDX.SDK.Contracts.Credential.ICredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.LoginResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.LoginResult> Login(PDX.SDK.Contracts.Credential.ICredential credential);
```

- `public abstract Logout() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Logout();
```

- `public abstract ReportPlayer(System.String reportedAccountId, System.String category) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> ReportPlayer(System.String reportedAccountId, System.String category);
```

- `public abstract ResetPassword(System.String email) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> ResetPassword(System.String email);
```

- `public abstract Startup() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.StartupResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Account.Result.StartupResult> Startup();
```

- `public abstract UpdateDetails(System.Nullable<PDX.SDK.Contracts.Enums.Language> language = null, System.Nullable<PDX.SDK.Contracts.Enums.Country> country = null, System.Nullable<System.DateTime> dateOfBirth = null, System.String firstName = null, System.String lastName = null, System.String addressLine1 = null, System.String addressLine2 = null, System.String city = null, System.String state = null, System.String zipCode = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> UpdateDetails(System.Nullable<PDX.SDK.Contracts.Enums.Language> language, System.Nullable<PDX.SDK.Contracts.Enums.Country> country, System.Nullable<System.DateTime> dateOfBirth, System.String firstName, System.String lastName, System.String addressLine1, System.String addressLine2, System.String city, System.String state, System.String zipCode);
```


