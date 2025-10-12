# Colossal.PSI.Common.ModEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public ModEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.PSI.Common.IModSupport psi, Colossal.PSI.Common.Mod mod) : System.Void`  

