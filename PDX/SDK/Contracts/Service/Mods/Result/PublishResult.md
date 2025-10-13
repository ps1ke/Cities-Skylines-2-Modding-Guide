# PDX.SDK.Contracts.Service.Mods.Result.PublishResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class PublishResult : PDX.SDK.Contracts.Result
{
    private System.Int32 <ModId>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;

    public System.Int32 ModId { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }

    public PublishResult();

}
```


## Fields

- `private System.Int32 <ModId>k__BackingField`  

```csharp
private System.Int32 <ModId>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Enums.ModState <State>k__BackingField;
```


## Properties

- `public System.Int32 ModId { get; set }`  

```csharp
public System.Int32 ModId { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Enums.ModState State { get; set; }
```


## Constructors

- `public PublishResult()`  

```csharp
public PublishResult();
```


