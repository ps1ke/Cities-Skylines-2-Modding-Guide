# Game.Input.InputManager+ActiveDeviceChanged

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ActiveDeviceChanged : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ActiveDeviceChanged(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
}
```


## Constructors

- `public ActiveDeviceChanged(System.Object object, System.IntPtr method)`  

```csharp
public ActiveDeviceChanged(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  

```csharp
public virtual System.Void Invoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
```


