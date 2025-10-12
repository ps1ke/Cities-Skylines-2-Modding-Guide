# Game.Input.InputManager+ActiveDeviceChanged

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public ActiveDeviceChanged(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  

