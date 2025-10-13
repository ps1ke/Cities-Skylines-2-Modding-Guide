# Colossal.PSI.Common.ITransferSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface ITransferSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    // (no members)
}
```


## Events

- `onTransferOnGoing` : `Colossal.PSI.Common.TransferEventHandler`  

```csharp
public event Colossal.PSI.Common.TransferEventHandler onTransferOnGoing;
```


