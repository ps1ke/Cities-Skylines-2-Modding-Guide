# Game.Input.UIBaseInputAction+DisplayGetter

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public DisplayGetter(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : Game.Input.DisplayNameOverride`  
- `public virtual Invoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform) : Game.Input.DisplayNameOverride`  

