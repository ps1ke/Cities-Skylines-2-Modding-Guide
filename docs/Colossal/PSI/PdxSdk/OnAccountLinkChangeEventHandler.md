# Colossal.PSI.PdxSdk.OnAccountLinkChangeEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public OnAccountLinkChangeEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.PSI.Common.AccountLinkState state, Colossal.PSI.Common.AccountLinkProvider provider) : System.Void`  

