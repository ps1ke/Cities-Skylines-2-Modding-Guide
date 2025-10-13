# Colossal.PSI.Common.OnConnectivityStatusChanged

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnConnectivityStatusChanged : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnConnectivityStatusChanged(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Boolean connected, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.Boolean connected);
}
```


## Constructors

- `public OnConnectivityStatusChanged(System.Object object, System.IntPtr method)`  

```csharp
public OnConnectivityStatusChanged(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Boolean connected, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Boolean connected, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Boolean connected) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Boolean connected);
```


