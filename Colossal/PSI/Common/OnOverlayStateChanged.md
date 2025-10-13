# Colossal.PSI.Common.OnOverlayStateChanged

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnOverlayStateChanged : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnOverlayStateChanged(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active);
}
```


## Constructors

- `public OnOverlayStateChanged(System.Object object, System.IntPtr method)`  

```csharp
public OnOverlayStateChanged(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active);
```


