# PDX.SDK.Contracts.Service.Mods.Result.GetGameDataResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class GetGameDataResult : PDX.SDK.Contracts.Result
{
    private System.String <Name>k__BackingField;
    private System.String <Extension>k__BackingField;
    private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Service.Generic.ITag> <Tags>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.GameActions <Actions>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.ModFilters <Filters>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> <Addons>k__BackingField;

    public System.String Name { get; set; }
    public System.String Extension { get; set; }
    public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Service.Generic.ITag> Tags { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.GameActions Actions { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.ModFilters Filters { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> Addons { get; set; }

    public GetGameDataResult();

}
```


## Fields

- `private System.String <Name>k__BackingField`  

```csharp
private System.String <Name>k__BackingField;
```

- `private System.String <Extension>k__BackingField`  

```csharp
private System.String <Extension>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Service.Generic.ITag> <Tags>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Service.Generic.ITag> <Tags>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.GameActions <Actions>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.GameActions <Actions>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.ModFilters <Filters>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.ModFilters <Filters>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> <Addons>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> <Addons>k__BackingField;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String Extension { get; set }`  

```csharp
public System.String Extension { get; set; }
```

- `public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Service.Generic.ITag> Tags { get; set }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Service.Generic.ITag> Tags { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.GameActions Actions { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.GameActions Actions { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.ModFilters Filters { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.ModFilters Filters { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> Addons { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> Addons { get; set; }
```


## Constructors

- `public GetGameDataResult()`  

```csharp
public GetGameDataResult();
```


