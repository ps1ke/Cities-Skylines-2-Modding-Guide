# Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Constructors

- `public OnLegalDocumentStatusChangedEventHandler(System.Object object, System.IntPtr method)`  

## Methods

- `public virtual BeginInvoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  
- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  
- `public virtual Invoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount) : System.Void`  

