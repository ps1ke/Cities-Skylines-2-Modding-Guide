# PDX.SDK.Contracts.Service.Mods.Result.ListSubscribedResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class ListSubscribedResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModDetails> <Mods>k__BackingField;
    private System.Nullable<System.DateTime> <LatestUpdate>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModDetails> Mods { get; set; }
    public System.Nullable<System.DateTime> LatestUpdate { get; set; }

    public ListSubscribedResult();

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModDetails> <Mods>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModDetails> <Mods>k__BackingField;
```

- `private System.Nullable<System.DateTime> <LatestUpdate>k__BackingField`  

```csharp
private System.Nullable<System.DateTime> <LatestUpdate>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModDetails> Mods { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModDetails> Mods { get; set; }
```

- `public System.Nullable<System.DateTime> LatestUpdate { get; set }`  

```csharp
public System.Nullable<System.DateTime> LatestUpdate { get; set; }
```


## Constructors

- `public ListSubscribedResult()`  

```csharp
public ListSubscribedResult();
```


