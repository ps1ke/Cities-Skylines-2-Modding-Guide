# Colossal.PSI.Common.IUserSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IUserSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public System.Boolean requiresEngagement { get; }
    public System.Boolean isUserSignedIn { get; }
    public System.String userName { get; }
    public System.Boolean supportsUserSwitching { get; }
    public System.Boolean supportsUserSection { get; }
    public System.String userSpecificPath { get; }
    public System.Boolean hasUgcPrivilege { get; }

    public abstract System.Void ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config);
    public abstract System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>> GetAvatar(Colossal.PSI.Common.AvatarSize size);
    public abstract System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags> SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback);
}
```


## Properties

- `public System.Boolean requiresEngagement { get }`  

```csharp
public System.Boolean requiresEngagement { get; }
```

- `public System.Boolean isUserSignedIn { get }`  

```csharp
public System.Boolean isUserSignedIn { get; }
```

- `public System.String userName { get }`  

```csharp
public System.String userName { get; }
```

- `public System.Boolean supportsUserSwitching { get }`  

```csharp
public System.Boolean supportsUserSwitching { get; }
```

- `public System.Boolean supportsUserSection { get }`  

```csharp
public System.Boolean supportsUserSection { get; }
```

- `public System.String userSpecificPath { get }`  

```csharp
public System.String userSpecificPath { get; }
```

- `public System.Boolean hasUgcPrivilege { get }`  

```csharp
public System.Boolean hasUgcPrivilege { get; }
```


## Methods

- `public abstract ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config) : System.Void`  

```csharp
public abstract System.Void ConfigurePdxSdkThirdParty(PDX.SDK.Contracts.Configuration.ThirdParty.ThirdPartyConfig config);
```

- `public abstract GetAvatar(Colossal.PSI.Common.AvatarSize size) : System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>>`  

```csharp
public abstract System.Threading.Tasks.Task<System.ValueTuple<System.Int32, System.Int32, System.Byte[]>> GetAvatar(Colossal.PSI.Common.AvatarSize size);
```

- `public abstract SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback) : System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags>`  

```csharp
public abstract System.Threading.Tasks.Task<Colossal.PSI.Common.SignInFlags> SignIn(Colossal.PSI.Common.SignInOptions signInOptions, System.Action<System.Threading.Tasks.Task> userChangingCallback);
```


## Events

- `onUserUpdated` : `Colossal.PSI.Common.OnUserUpdatedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnUserUpdatedEventHandler onUserUpdated;
```


