# PDX.SDK.Internal.Service.Mods.Models.PlaysetMetaData

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Service.Mods.Models`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class PlaysetMetaData
{
    private System.Int32 <ContractFormatVersion>k__BackingField;
    private PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData <GeneralData>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData> <SubscribedMods>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData> <WipMods>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData> <UnmanagedMods>k__BackingField;

    public System.Int32 ContractFormatVersion { get; private set; }
    public PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData GeneralData { get; set; }
    public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData> SubscribedMods { get; set; }
    public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData> WipMods { get; set; }
    public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData> UnmanagedMods { get; set; }

    public PlaysetMetaData();

}
```


## Fields

- `private System.Int32 <ContractFormatVersion>k__BackingField`  

```csharp
private System.Int32 <ContractFormatVersion>k__BackingField;
```

- `private PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData <GeneralData>k__BackingField`  

```csharp
private PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData <GeneralData>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData> <SubscribedMods>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData> <SubscribedMods>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData> <WipMods>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData> <WipMods>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData> <UnmanagedMods>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData> <UnmanagedMods>k__BackingField;
```


## Properties

- `public System.Int32 ContractFormatVersion { get; private set }`  

```csharp
public System.Int32 ContractFormatVersion { get; private set; }
```

- `public PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData GeneralData { get; set }`  

```csharp
public PDX.SDK.Internal.Service.Mods.Models.PlaysetGeneralMetaData GeneralData { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData> SubscribedMods { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetSubscribedModMetaData> SubscribedMods { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData> WipMods { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetWipModMetaData> WipMods { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData> UnmanagedMods { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Internal.Service.Mods.Models.PlaysetUnmanagedModMetaData> UnmanagedMods { get; set; }
```


## Constructors

- `public PlaysetMetaData()`  

```csharp
public PlaysetMetaData();
```


