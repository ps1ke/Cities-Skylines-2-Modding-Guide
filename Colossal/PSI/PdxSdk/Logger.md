# Colossal.PSI.PdxSdk.PdxSdkPlatform+Logger

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Contracts.Logging.ILogger`  

## Code

```csharp
public class Logger : PDX.SDK.Contracts.Logging.ILogger
{
    public Logger();

    public System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
}
```


## Constructors

- `public Logger()`  

```csharp
public Logger();
```


## Methods

- `public Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
public System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
```


