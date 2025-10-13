# PDX.SDK.Contracts.Service.Loyalty.Result.LoyaltyStatusResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Loyalty.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class LoyaltyStatusResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.Campaign> <Campaigns>k__BackingField;
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.ThresholdReached> <ThresholdsReached>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.Campaign> Campaigns { get; set; }
    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.ThresholdReached> ThresholdsReached { get; set; }

    public LoyaltyStatusResult();

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.Campaign> <Campaigns>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.Campaign> <Campaigns>k__BackingField;
```

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.ThresholdReached> <ThresholdsReached>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.ThresholdReached> <ThresholdsReached>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.Campaign> Campaigns { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.Campaign> Campaigns { get; set; }
```

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.ThresholdReached> ThresholdsReached { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Loyalty.Models.ThresholdReached> ThresholdsReached { get; set; }
```


## Constructors

- `public LoyaltyStatusResult()`  

```csharp
public LoyaltyStatusResult();
```


