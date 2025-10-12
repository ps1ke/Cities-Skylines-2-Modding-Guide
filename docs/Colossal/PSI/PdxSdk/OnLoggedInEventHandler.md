# Colossal.PSI.PdxSdk.OnLoggedInEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public OnLoggedInEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(System.String firstName, System.String lastName, System.String email, Colossal.PSI.Common.AccountLinkState accountLinkState, System.Boolean firstTime) : System.Void`  

