# Colossal.PSI.Common.IDeviceAssociationSupport

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  

**Implements:** `Colossal.PSI.Common.IPlatformServiceIntegration`, `Colossal.PSI.Common.IDisposableAsync`  

## Code

```csharp
public abstract interface IDeviceAssociationSupport : Colossal.PSI.Common.IPlatformServiceIntegration, Colossal.PSI.Common.IDisposableAsync
{
    public abstract System.Threading.Tasks.Task<System.Boolean> AssociateDevice(UnityEngine.InputSystem.InputDevice device);
    public abstract System.Boolean IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device);
}
```


## Methods

- `public abstract AssociateDevice(UnityEngine.InputSystem.InputDevice device) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public abstract System.Threading.Tasks.Task<System.Boolean> AssociateDevice(UnityEngine.InputSystem.InputDevice device);
```

- `public abstract IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  

```csharp
public abstract System.Boolean IsDeviceAssociated(UnityEngine.InputSystem.InputDevice device);
```


## Events

- `onDeviceAssociationChanged` : `Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler`  

```csharp
public event Colossal.PSI.Common.OnDeviceAssociationChangedEventHandler onDeviceAssociationChanged;
```


