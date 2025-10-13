# PDX.SDK.Contracts.Service.Telemetry.ITelemetryService

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Telemetry`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ITelemetryService
{
    public System.Boolean IsEnabled { get; }

    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Exit();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult> GetTelemetryConsentChoice();
    public abstract System.Threading.Tasks.Task<System.Boolean> IsTelemetryConsentPresentable();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.SendResult> Send<T>(System.Collections.Generic.IList<T> events);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.SendResult> Send<T>(T event);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SendOptionalTelemetrySettingWhenFallback();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SendOptionalTelemetrySettingWhenSetByPlayer(System.Boolean consent);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.UnityInfoResult> SendUnityInfo();
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SetTelemetryConsentChoice(System.Boolean allowed);
    public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Start();
}
```


## Properties

- `public System.Boolean IsEnabled { get }`  

```csharp
public System.Boolean IsEnabled { get; }
```


## Methods

- `public abstract Exit() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Exit();
```

- `public abstract GetTelemetryConsentChoice() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.GetConsentChoiceResult> GetTelemetryConsentChoice();
```

- `public abstract IsTelemetryConsentPresentable() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> IsTelemetryConsentPresentable();
```

- `public abstract Send<T>(System.Collections.Generic.IList<T> events) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.SendResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.SendResult> Send<T>(System.Collections.Generic.IList<T> events);
```

- `public abstract Send<T>(T event) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.SendResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.SendResult> Send<T>(T event);
```

- `public abstract SendOptionalTelemetrySettingWhenFallback() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SendOptionalTelemetrySettingWhenFallback();
```

- `public abstract SendOptionalTelemetrySettingWhenSetByPlayer(System.Boolean consent) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SendOptionalTelemetrySettingWhenSetByPlayer(System.Boolean consent);
```

- `public abstract SendUnityInfo() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.UnityInfoResult>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Service.Telemetry.Result.UnityInfoResult> SendUnityInfo();
```

- `public abstract SetTelemetryConsentChoice(System.Boolean allowed) : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> SetTelemetryConsentChoice(System.Boolean allowed);
```

- `public abstract Start() : System.Threading.Tasks.Task<PDX.SDK.Contracts.Result>`  

```csharp
public abstract System.Threading.Tasks.Task<PDX.SDK.Contracts.Result> Start();
```


