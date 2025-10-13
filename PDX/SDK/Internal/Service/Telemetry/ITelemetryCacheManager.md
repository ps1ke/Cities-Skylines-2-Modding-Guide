# PDX.SDK.Internal.Service.Telemetry.ITelemetryCacheManager

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Service.Telemetry`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ITelemetryCacheManager
{
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult> GetTelemetryConsentChoice(PDX.SDK.Contracts.Internal.FlowData flowData);
    public abstract System.Threading.Tasks.Task<System.Boolean> IsTelemetryConsentPresentable();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> LoadTelemetryCache(PDX.SDK.Contracts.Internal.FlowData flowData);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SetTelemetryConsentChoice(System.Boolean allowed, PDX.SDK.Contracts.Internal.FlowData flowData);
}
```


## Methods

- `public abstract GetTelemetryConsentChoice(PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult> GetTelemetryConsentChoice(PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public abstract IsTelemetryConsentPresentable() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> IsTelemetryConsentPresentable();
```

- `public abstract LoadTelemetryCache(PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> LoadTelemetryCache(PDX.SDK.Contracts.Internal.FlowData flowData);
```

- `public abstract SetTelemetryConsentChoice(System.Boolean allowed, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SetTelemetryConsentChoice(System.Boolean allowed, PDX.SDK.Contracts.Internal.FlowData flowData);
```


