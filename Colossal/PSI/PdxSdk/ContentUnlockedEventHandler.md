# Colossal.PSI.PdxSdk.ContentUnlockedEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class ContentUnlockedEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public ContentUnlockedEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlc, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlc);
}
```


## Constructors

- `public ContentUnlockedEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public ContentUnlockedEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlc, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlc, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlc) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Collections.Generic.List<Colossal.PSI.Common.IDlc> dlc);
```


