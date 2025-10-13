# PDX.SDK.Contracts.Configuration.ThirdParty.SteamConfig

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Configuration.ThirdParty`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SteamConfig
{
    private System.Nullable<System.Boolean> <Enabled>k__BackingField;
    private System.String <Ticket>k__BackingField;
    private System.Nullable<System.UInt32> <AppId>k__BackingField;

    public System.Nullable<System.Boolean> Enabled { get; set; }
    public System.String Ticket { get; set; }
    public System.Nullable<System.UInt32> AppId { get; set; }

    public SteamConfig();

    public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.ThirdParty.SteamConfig cfg);
}
```


## Fields

- `private System.Nullable<System.Boolean> <Enabled>k__BackingField`  

```csharp
private System.Nullable<System.Boolean> <Enabled>k__BackingField;
```

- `private System.String <Ticket>k__BackingField`  

```csharp
private System.String <Ticket>k__BackingField;
```

- `private System.Nullable<System.UInt32> <AppId>k__BackingField`  

```csharp
private System.Nullable<System.UInt32> <AppId>k__BackingField;
```


## Properties

- `public System.Nullable<System.Boolean> Enabled { get; set }`  

```csharp
public System.Nullable<System.Boolean> Enabled { get; set; }
```

- `public System.String Ticket { get; set }`  

```csharp
public System.String Ticket { get; set; }
```

- `public System.Nullable<System.UInt32> AppId { get; set }`  

```csharp
public System.Nullable<System.UInt32> AppId { get; set; }
```


## Constructors

- `public SteamConfig()`  

```csharp
public SteamConfig();
```


## Methods

- `public SetIfNotNull(PDX.SDK.Contracts.Configuration.ThirdParty.SteamConfig cfg) : System.Void`  

```csharp
public System.Void SetIfNotNull(PDX.SDK.Contracts.Configuration.ThirdParty.SteamConfig cfg);
```


