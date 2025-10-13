# PDX.SDK.Contracts.Service.Mods.Result.SubscribeResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class SubscribeResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSubscribeStatus> <ModsSubscribedStatus>k__BackingField;
    private System.Int32 <PlaysetId>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSubscribeStatus> ModsSubscribedStatus { get; set; }
    public System.Int32 PlaysetId { get; set; }

    public SubscribeResult();

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSubscribeStatus> <ModsSubscribedStatus>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSubscribeStatus> <ModsSubscribedStatus>k__BackingField;
```

- `private System.Int32 <PlaysetId>k__BackingField`  

```csharp
private System.Int32 <PlaysetId>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSubscribeStatus> ModsSubscribedStatus { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModSubscribeStatus> ModsSubscribedStatus { get; set; }
```

- `public System.Int32 PlaysetId { get; set }`  

```csharp
public System.Int32 PlaysetId { get; set; }
```


## Constructors

- `public SubscribeResult()`  

```csharp
public SubscribeResult();
```


