# Colossal.PSI.Common.ITelemetrySupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface ITelemetrySupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public abstract System.Boolean GetTelemetryConsentChoice();
    public abstract System.Boolean IsTelemetryConsentPresentable();
    public abstract System.Void SendTelemetry<T>(System.String eventName, T payload);
    public abstract System.Threading.Tasks.Task<System.Boolean> SetTelemetryConsentChoice(System.Boolean allowed);
    public abstract System.Void SyncTelemetryConsentChoice();
}
```


## Methods

- `public abstract GetTelemetryConsentChoice() : System.Boolean`  

```csharp
public abstract System.Boolean GetTelemetryConsentChoice();
```

- `public abstract IsTelemetryConsentPresentable() : System.Boolean`  

```csharp
public abstract System.Boolean IsTelemetryConsentPresentable();
```

- `public abstract SendTelemetry<T>(System.String eventName, T payload) : System.Void`  

```csharp
public abstract System.Void SendTelemetry<T>(System.String eventName, T payload);
```

- `public abstract SetTelemetryConsentChoice(System.Boolean allowed) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> SetTelemetryConsentChoice(System.Boolean allowed);
```

- `public abstract SyncTelemetryConsentChoice() : System.Void`  

```csharp
public abstract System.Void SyncTelemetryConsentChoice();
```


