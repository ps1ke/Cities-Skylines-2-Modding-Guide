# Colossal.PSI.Common.ModInstallProgressEventHandler

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public ModInstallProgressEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus transfer, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.PSI.Common.IModSupport psi, System.Int32 modId, Colossal.PSI.Common.TransferStatus transfer) : System.Void`  

