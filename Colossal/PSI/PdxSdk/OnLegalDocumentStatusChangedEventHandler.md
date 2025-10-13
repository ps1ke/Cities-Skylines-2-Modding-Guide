# Colossal.PSI.PdxSdk.OnLegalDocumentStatusChangedEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnLegalDocumentStatusChangedEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnLegalDocumentStatusChangedEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount);
}
```


## Constructors

- `public OnLegalDocumentStatusChangedEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public OnLegalDocumentStatusChangedEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.PSI.PdxSdk.LegalDocument document, System.Int32 remainingCount);
```


