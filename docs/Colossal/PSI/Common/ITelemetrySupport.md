# Colossal.PSI.Common.ITelemetrySupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Methods

- `public abstract GetTelemetryConsentChoice() : System.Boolean`  
- `public abstract IsTelemetryConsentPresentable() : System.Boolean`  
- `public abstract SendTelemetry<T>(System.String eventName, T payload) : System.Void`  
- `public abstract SetTelemetryConsentChoice(System.Boolean allowed) : System.Threading.Tasks.Task<System.Boolean>`  
- `public abstract SyncTelemetryConsentChoice() : System.Void`  

