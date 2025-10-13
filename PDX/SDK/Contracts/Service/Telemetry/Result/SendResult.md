# PDX.SDK.Contracts.Service.Telemetry.Result.SendResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class SendResult : PDX.SDK.Contracts.Result
{
    private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.RejectedEvent> <RejectedEvents>k__BackingField;

    public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.RejectedEvent> RejectedEvents { get; set; }

    public SendResult();

}
```


## Fields

- `private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.RejectedEvent> <RejectedEvents>k__BackingField`  

```csharp
private System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.RejectedEvent> <RejectedEvents>k__BackingField;
```


## Properties

- `public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.RejectedEvent> RejectedEvents { get; set }`  

```csharp
public System.Collections.Generic.List<PDX.SDK.Contracts.Service.Telemetry.Models.RejectedEvent> RejectedEvents { get; set; }
```


## Constructors

- `public SendResult()`  

```csharp
public SendResult();
```


