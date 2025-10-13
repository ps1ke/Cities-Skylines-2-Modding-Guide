# PDX.SDK.Contracts.Service.Profile.IProfileService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Profile`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IProfileService
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CreateGameDisplayName(System.String displayName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CreateSocialDisplayName(System.String displayName);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Profile.Result.GetProfileResult> Get();
}
```


## Methods

- `public abstract CreateGameDisplayName(System.String displayName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CreateGameDisplayName(System.String displayName);
```

- `public abstract CreateSocialDisplayName(System.String displayName) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> CreateSocialDisplayName(System.String displayName);
```

- `public abstract Get() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Profile.Result.GetProfileResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Profile.Result.GetProfileResult> Get();
```


