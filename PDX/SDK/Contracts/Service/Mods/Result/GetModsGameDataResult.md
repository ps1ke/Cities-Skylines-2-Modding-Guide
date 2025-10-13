# PDX.SDK.Contracts.Service.Mods.Result.GetModsGameDataResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class GetModsGameDataResult : PDX.SDK.Contracts.Result
{
    private PDX.SDK.Contracts.Service.Mods.Models.ModFilters <Filters>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> <Addons>k__BackingField;

    public PDX.SDK.Contracts.Service.Mods.Models.ModFilters Filters { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> Addons { get; set; }

    public GetModsGameDataResult();

}
```


## Fields

- `private PDX.SDK.Contracts.Service.Mods.Models.ModFilters <Filters>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.ModFilters <Filters>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> <Addons>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> <Addons>k__BackingField;
```


## Properties

- `public PDX.SDK.Contracts.Service.Mods.Models.ModFilters Filters { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.ModFilters Filters { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> Addons { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> Addons { get; set; }
```


## Constructors

- `public GetModsGameDataResult()`  

```csharp
public GetModsGameDataResult();
```


