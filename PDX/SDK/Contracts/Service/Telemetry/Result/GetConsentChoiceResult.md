# PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

## Code

```csharp
public class GetConsentChoiceResult : PDX.SDK.Contracts.Result
{
    private System.Boolean <ConsentChoice>k__BackingField;
    private PDX.SDK.Contracts.Service.Telemetry.TelemetryConsentSourceEnum <ConsentChoiceSource>k__BackingField;

    public System.Boolean ConsentChoice { get; set; }
    public PDX.SDK.Contracts.Service.Telemetry.TelemetryConsentSourceEnum ConsentChoiceSource { get; set; }

    public GetConsentChoiceResult();

}
```


## Fields

- `private System.Boolean <ConsentChoice>k__BackingField`  

```csharp
private System.Boolean <ConsentChoice>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Telemetry.TelemetryConsentSourceEnum <ConsentChoiceSource>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Telemetry.TelemetryConsentSourceEnum <ConsentChoiceSource>k__BackingField;
```


## Properties

- `public System.Boolean ConsentChoice { get; set }`  

```csharp
public System.Boolean ConsentChoice { get; set; }
```

- `public PDX.SDK.Contracts.Service.Telemetry.TelemetryConsentSourceEnum ConsentChoiceSource { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Telemetry.TelemetryConsentSourceEnum ConsentChoiceSource { get; set; }
```


## Constructors

- `public GetConsentChoiceResult()`  

```csharp
public GetConsentChoiceResult();
```


