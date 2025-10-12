# Colossal.PSI.Common.IPlatformServiceIntegration

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IDisposableAsync`  

## Properties

- `public System.String name { get }`  
- `public System.Boolean isInitialized { get }`  

## Methods

- `public abstract Initialize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  
- `public abstract LogVersion(System.Text.StringBuilder b) : System.Void`  
- `public abstract Update() : System.Void`  

## Events

- `onStatusChanged` : `Colossal.PSI.Common.OnStatusChangedEventHandler`  

