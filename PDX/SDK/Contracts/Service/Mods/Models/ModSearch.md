# PDX.SDK.Contracts.Service.Mods.Models.ModSearch

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Models`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Mods.Models.Mod`  
**Implements:** `PDX.SDK.Contracts.Service.Mods.Models.IMod`  

## Code

```csharp
public class ModSearch : PDX.SDK.Contracts.Service.Mods.Models.Mod, PDX.SDK.Contracts.Service.Mods.Models.IMod
{
    private System.Boolean <IsSubscribed>k__BackingField;
    private System.Nullable<System.DateTime> <SubscriptionDate>k__BackingField;
    private System.Boolean <IsEnabled>k__BackingField;
    private System.Int32 <InstalledCount>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> <ThirdPartyProfiles>k__BackingField;

    public System.Boolean IsSubscribed { get; set; }
    public System.Nullable<System.DateTime> SubscriptionDate { get; set; }
    public System.Boolean IsEnabled { get; set; }
    public System.Int32 InstalledCount { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> ThirdPartyProfiles { get; set; }

    public ModSearch();

}
```


## Fields

- `private System.Boolean <IsSubscribed>k__BackingField`  

```csharp
private System.Boolean <IsSubscribed>k__BackingField;
```

- `private System.Nullable<System.DateTime> <SubscriptionDate>k__BackingField`  

```csharp
private System.Nullable<System.DateTime> <SubscriptionDate>k__BackingField;
```

- `private System.Boolean <IsEnabled>k__BackingField`  

```csharp
private System.Boolean <IsEnabled>k__BackingField;
```

- `private System.Int32 <InstalledCount>k__BackingField`  

```csharp
private System.Int32 <InstalledCount>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> <ThirdPartyProfiles>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> <ThirdPartyProfiles>k__BackingField;
```


## Properties

- `public System.Boolean IsSubscribed { get; set }`  

```csharp
public System.Boolean IsSubscribed { get; set; }
```

- `public System.Nullable<System.DateTime> SubscriptionDate { get; set }`  

```csharp
public System.Nullable<System.DateTime> SubscriptionDate { get; set; }
```

- `public System.Boolean IsEnabled { get; set }`  

```csharp
public System.Boolean IsEnabled { get; set; }
```

- `public System.Int32 InstalledCount { get; set }`  

```csharp
public System.Int32 InstalledCount { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> ThirdPartyProfiles { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.ThirdParty.Models.ThirdPartyProfile> ThirdPartyProfiles { get; set; }
```


## Constructors

- `public ModSearch()`  

```csharp
public ModSearch();
```


