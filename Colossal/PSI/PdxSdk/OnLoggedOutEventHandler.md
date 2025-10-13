# Colossal.PSI.PdxSdk.OnLoggedOutEventHandler

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnLoggedOutEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnLoggedOutEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String id, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String id);
}
```


## Constructors

- `public OnLoggedOutEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public OnLoggedOutEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String id, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String id, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String id) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String id);
```


