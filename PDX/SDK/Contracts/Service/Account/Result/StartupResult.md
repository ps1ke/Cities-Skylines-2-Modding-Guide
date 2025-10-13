# PDX.SDK.Contracts.Service.Account.Result.StartupResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Account.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Account.Result.LoginResult`  

**Attributes:** `Preserve`  

## Code

```csharp
public class StartupResult : PDX.SDK.Contracts.Service.Account.Result.LoginResult
{
    private System.Boolean <IsLoggedIn>k__BackingField;
    private PDX.SDK.Contracts.Enums.AutoLoginPromptState <AutoLoginPromptState>k__BackingField;

    public System.Boolean IsLoggedIn { get; set; }
    public PDX.SDK.Contracts.Enums.AutoLoginPromptState AutoLoginPromptState { get; set; }

    public StartupResult();
    public StartupResult(PDX.SDK.Contracts.Service.Account.Result.LoginResult login, PDX.SDK.Contracts.Enums.AutoLoginPromptState autoLoginPromptState);

}
```


## Fields

- `private System.Boolean <IsLoggedIn>k__BackingField`  

```csharp
private System.Boolean <IsLoggedIn>k__BackingField;
```

- `private PDX.SDK.Contracts.Enums.AutoLoginPromptState <AutoLoginPromptState>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Enums.AutoLoginPromptState <AutoLoginPromptState>k__BackingField;
```


## Properties

- `public System.Boolean IsLoggedIn { get; set }`  

```csharp
public System.Boolean IsLoggedIn { get; set; }
```

- `public PDX.SDK.Contracts.Enums.AutoLoginPromptState AutoLoginPromptState { get; set }`  

```csharp
public PDX.SDK.Contracts.Enums.AutoLoginPromptState AutoLoginPromptState { get; set; }
```


## Constructors

- `public StartupResult()`  

```csharp
public StartupResult();
```

- `public StartupResult(PDX.SDK.Contracts.Service.Account.Result.LoginResult login, PDX.SDK.Contracts.Enums.AutoLoginPromptState autoLoginPromptState = PromptNotShown)`  

```csharp
public StartupResult(PDX.SDK.Contracts.Service.Account.Result.LoginResult login, PDX.SDK.Contracts.Enums.AutoLoginPromptState autoLoginPromptState);
```


