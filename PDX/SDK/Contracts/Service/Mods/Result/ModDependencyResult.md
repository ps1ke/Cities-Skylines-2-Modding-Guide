# PDX.SDK.Contracts.Service.Mods.Result.ModDependencyResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Mods.Models.ModDependency`  

## Code

```csharp
public class ModDependencyResult : PDX.SDK.Contracts.Service.Mods.Models.ModDependency
{
    private System.UInt64 <Size>k__BackingField;
    private System.Int32 <LoadOrder>k__BackingField;
    private System.Boolean <IsSubscribed>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;

    public System.UInt64 Size { get; set; }
    public System.Int32 LoadOrder { get; set; }
    public System.Boolean IsSubscribed { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }

    public ModDependencyResult();

}
```


## Fields

- `private System.UInt64 <Size>k__BackingField`  

```csharp
private System.UInt64 <Size>k__BackingField;
```

- `private System.Int32 <LoadOrder>k__BackingField`  

```csharp
private System.Int32 <LoadOrder>k__BackingField;
```

- `private System.Boolean <IsSubscribed>k__BackingField`  

```csharp
private System.Boolean <IsSubscribed>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;
```


## Properties

- `public System.UInt64 Size { get; set }`  

```csharp
public System.UInt64 Size { get; set; }
```

- `public System.Int32 LoadOrder { get; set }`  

```csharp
public System.Int32 LoadOrder { get; set; }
```

- `public System.Boolean IsSubscribed { get; set }`  

```csharp
public System.Boolean IsSubscribed { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
```


## Constructors

- `public ModDependencyResult()`  

```csharp
public ModDependencyResult();
```


