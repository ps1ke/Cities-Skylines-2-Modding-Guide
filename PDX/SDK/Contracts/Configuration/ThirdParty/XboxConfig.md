# PDX.SDK.Contracts.Configuration.ThirdParty.XboxConfig

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Configuration.ThirdParty`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class XboxConfig
{
    private System.Nullable<System.Boolean> <Enabled>k__BackingField;
    public Unity.XGamingRuntime.XUserHandle UserHandle;
    public Unity.XGamingRuntime.XGameSaveProviderHandle GameSaveProviderHandle;
    public System.String Scid;
    public Unity.XGamingRuntime.XblContextHandle ContextHandle;

    public System.Nullable<System.Boolean> Enabled { get; set; }

    public XboxConfig();

    public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.ThirdParty.XboxConfig cfg);
}
```


## Fields

- `private System.Nullable<System.Boolean> <Enabled>k__BackingField`  

```csharp
private System.Nullable<System.Boolean> <Enabled>k__BackingField;
```

- `public Unity.XGamingRuntime.XUserHandle UserHandle`  

```csharp
public Unity.XGamingRuntime.XUserHandle UserHandle;
```

- `public Unity.XGamingRuntime.XGameSaveProviderHandle GameSaveProviderHandle`  

```csharp
public Unity.XGamingRuntime.XGameSaveProviderHandle GameSaveProviderHandle;
```

- `public System.String Scid`  

```csharp
public System.String Scid;
```

- `public Unity.XGamingRuntime.XblContextHandle ContextHandle`  

```csharp
public Unity.XGamingRuntime.XblContextHandle ContextHandle;
```


## Properties

- `public System.Nullable<System.Boolean> Enabled { get; set }`  

```csharp
public System.Nullable<System.Boolean> Enabled { get; set; }
```


## Constructors

- `public XboxConfig()`  

```csharp
public XboxConfig();
```


## Methods

- `public SetIfNotNull(PDX.SDK.Contracts.Configuration.ThirdParty.XboxConfig cfg) : System.Void`  

```csharp
public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.ThirdParty.XboxConfig cfg);
```


