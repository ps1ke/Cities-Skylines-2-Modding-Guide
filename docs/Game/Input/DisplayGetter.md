# Game.Input.UIBaseInputAction+DisplayGetter

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class DisplayGetter : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public DisplayGetter(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform, System.AsyncCallback callback, System.Object object);
    public virtual Game.Input.DisplayNameOverride EndInvoke(System.IAsyncResult result);
    public virtual Game.Input.DisplayNameOverride Invoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform);
}
```


## Constructors

- `public DisplayGetter(System.Object object, System.IntPtr method)`  

```csharp
public DisplayGetter(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : Game.Input.DisplayNameOverride`  

```csharp
public virtual Game.Input.DisplayNameOverride EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform) : Game.Input.DisplayNameOverride`  

```csharp
public virtual Game.Input.DisplayNameOverride Invoke(System.String name, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask, Game.Input.UIBaseInputAction+Transform transform);
```


