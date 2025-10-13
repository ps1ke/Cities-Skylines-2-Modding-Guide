# PDX.SDK.Contracts.Logging.ILogger

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Logging`  

**Type:** interface abstract public  


**Attributes:** `Preserve`  

## Code

```csharp
public abstract interface ILogger
{
    public abstract System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
}
```


## Methods

- `public abstract Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel = L1_Debug, PDX.SDK.Contracts.Internal.FlowData flowData = null) : System.Void`  

```csharp
public abstract System.Void Log(System.String msg, PDX.SDK.Contracts.Enums.LogLevel logLevel, PDX.SDK.Contracts.Internal.FlowData flowData);
```


