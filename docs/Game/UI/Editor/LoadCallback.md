# Game.UI.Editor.LoadAssetPanel+LoadCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public LoadCallback(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.Hash128 guid, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.Hash128 guid) : System.Void`  

