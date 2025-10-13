# PDX.SDK.Contracts.Service.Mods.Result.ModSearchResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class ModSearchResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSearch> <Mods>k__BackingField;
    private System.Int32 <TotalCount>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSearch> Mods { get; set; }
    public System.Int32 TotalCount { get; set; }

    public ModSearchResult();

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSearch> <Mods>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSearch> <Mods>k__BackingField;
```

- `private System.Int32 <TotalCount>k__BackingField`  

```csharp
private System.Int32 <TotalCount>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSearch> Mods { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSearch> Mods { get; set; }
```

- `public System.Int32 TotalCount { get; set }`  

```csharp
public System.Int32 TotalCount { get; set; }
```


## Constructors

- `public ModSearchResult()`  

```csharp
public ModSearchResult();
```


