# Game.UI.Widgets.ValueChangedCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public ValueChangedCallback(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Game.UI.Widgets.IWidget widget, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Game.UI.Widgets.IWidget widget) : System.Void`  

