# PDX.SDK.Contracts.Service.Telemetry.Result.UnityInfoResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Service.Telemetry.Result.SendResult`  

## Code

```csharp
public class UnityInfoResult : PDX.SDK.Contracts.Service.Telemetry.Result.SendResult
{
    private PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo <UnityInfo>k__BackingField;

    public PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo UnityInfo { get; set; }

    public UnityInfoResult(PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo info, PDX.SDK.Contracts.Service.Telemetry.Result.SendResult result);

}
```


## Fields

- `private PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo <UnityInfo>k__BackingField`  

```csharp
private PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo <UnityInfo>k__BackingField;
```


## Properties

- `public PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo UnityInfo { get; set }`  

```csharp
public PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo UnityInfo { get; set; }
```


## Constructors

- `public UnityInfoResult(PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo info, PDX.SDK.Contracts.Service.Telemetry.Result.SendResult result)`  

```csharp
public UnityInfoResult(PDX.SDK.Internal.Service.Telemetry.Models.UnityInfo info, PDX.SDK.Contracts.Service.Telemetry.Result.SendResult result);
```


