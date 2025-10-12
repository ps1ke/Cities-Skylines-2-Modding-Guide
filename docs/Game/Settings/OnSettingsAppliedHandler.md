# Game.Settings.OnSettingsAppliedHandler

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public OnSettingsAppliedHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Game.Settings.Setting setting, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Game.Settings.Setting setting) : System.Void`  

