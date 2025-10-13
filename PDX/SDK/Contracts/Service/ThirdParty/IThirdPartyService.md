# PDX.SDK.Contracts.Service.ThirdParty.IThirdPartyService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.ThirdParty`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IThirdPartyService
{
    public PDX.SDK.Contracts.Service.ThirdParty.INintendoSwitchService NintendoSwitch { get; }

    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.ThirdParty.Result.GetAccountLinksResult> GetAccountLinks();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.ThirdParty.Result.GetAccountLinksResult> GetAccountLinks(PDX.SDK.Contracts.Credential.ICredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.AppleSignInCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.GoogleCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.StadiaCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.SteamCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.NintendoAccountCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.PsnCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.XboxLiveCredential credential);
    public abstract System.Threading.Tasks.Task SetAutoLoginPromptState(PDX.SDK.Contracts.Enums.AutoLoginPromptState autoLoginPromptState);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.AppleSignInCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.GoogleCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.StadiaCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.SteamCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.NintendoAccountCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider provider);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.PsnCredential credential);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.XboxLiveCredential credential);
}
```


## Properties

- `public PDX.SDK.Contracts.Service.ThirdParty.INintendoSwitchService NintendoSwitch { get }`  

```csharp
public PDX.SDK.Contracts.Service.ThirdParty.INintendoSwitchService NintendoSwitch { get; }
```


## Methods

- `public abstract GetAccountLinks() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.ThirdParty.Result.GetAccountLinksResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.ThirdParty.Result.GetAccountLinksResult> GetAccountLinks();
```

- `public abstract GetAccountLinks(PDX.SDK.Contracts.Credential.ICredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.ThirdParty.Result.GetAccountLinksResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.ThirdParty.Result.GetAccountLinksResult> GetAccountLinks(PDX.SDK.Contracts.Credential.ICredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.AppleSignInCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.AppleSignInCredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.GoogleCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.GoogleCredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.StadiaCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.StadiaCredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.SteamCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.SteamCredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.NintendoAccountCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.NintendoAccountCredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.PsnCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.PsnCredential credential);
```

- `public abstract Link(PDX.SDK.Contracts.Credential.XboxLiveCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Link(PDX.SDK.Contracts.Credential.XboxLiveCredential credential);
```

- `public abstract SetAutoLoginPromptState(PDX.SDK.Contracts.Enums.AutoLoginPromptState autoLoginPromptState) : System.Threading.Tasks.Task`  

```csharp
public abstract System.Threading.Tasks.Task SetAutoLoginPromptState(PDX.SDK.Contracts.Enums.AutoLoginPromptState autoLoginPromptState);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.AppleSignInCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.AppleSignInCredential credential);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.GoogleCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.GoogleCredential credential);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.StadiaCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.StadiaCredential credential);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.SteamCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.SteamCredential credential);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.NintendoAccountCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.NintendoAccountCredential credential);
```

- `public abstract Unlink(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider provider) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Service.ThirdParty.Enums.Provider provider);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.PsnCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.PsnCredential credential);
```

- `public abstract Unlink(PDX.SDK.Contracts.Credential.XboxLiveCredential credential) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Unlink(PDX.SDK.Contracts.Credential.XboxLiveCredential credential);
```


