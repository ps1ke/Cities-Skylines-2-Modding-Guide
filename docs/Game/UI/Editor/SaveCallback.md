# Game.UI.Editor.SaveAssetPanel+SaveCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public SaveCallback(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(System.String name, System.Nullable<Colossal.Hash128> overwriteGuid) : System.Void`  

