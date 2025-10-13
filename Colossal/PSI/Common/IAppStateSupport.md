# Colossal.PSI.Common.IAppStateSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IAppStateSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    // (no members)
}
```


## Events

- `onAppStateChanged` : `Colossal.PSI.Common.OnAppStateChanged`  

```csharp
public event Colossal.PSI.Common.OnAppStateChanged onAppStateChanged;
```


