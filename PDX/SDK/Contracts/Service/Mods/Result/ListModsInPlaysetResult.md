# PDX.SDK.Contracts.Service.Mods.Result.ListModsInPlaysetResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class ListModsInPlaysetResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod> <Mods>k__BackingField;
    private System.Int32 <TotalCount>k__BackingField;
    private System.Int32 <Page>k__BackingField;
    private System.Int32 <Limit>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod> Mods { get; set; }
    public System.Int32 TotalCount { get; set; }
    public System.Int32 Page { get; set; }
    public System.Int32 Limit { get; set; }

    public ListModsInPlaysetResult();

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod> <Mods>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod> <Mods>k__BackingField;
```

- `private System.Int32 <TotalCount>k__BackingField`  

```csharp
private System.Int32 <TotalCount>k__BackingField;
```

- `private System.Int32 <Page>k__BackingField`  

```csharp
private System.Int32 <Page>k__BackingField;
```

- `private System.Int32 <Limit>k__BackingField`  

```csharp
private System.Int32 <Limit>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod> Mods { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.IPlaysetMod> Mods { get; set; }
```

- `public System.Int32 TotalCount { get; set }`  

```csharp
public System.Int32 TotalCount { get; set; }
```

- `public System.Int32 Page { get; set }`  

```csharp
public System.Int32 Page { get; set; }
```

- `public System.Int32 Limit { get; set }`  

```csharp
public System.Int32 Limit { get; set; }
```


## Constructors

- `public ListModsInPlaysetResult()`  

```csharp
public ListModsInPlaysetResult();
```


