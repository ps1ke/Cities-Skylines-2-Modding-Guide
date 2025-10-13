# Colossal.UI.UISystem+OnHostLocationRemoved

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnHostLocationRemoved : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnHostLocationRemoved(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String uri, System.String path, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String uri, System.String path);
}
```


## Constructors

- `public OnHostLocationRemoved(System.Object object, System.IntPtr method)`  

```csharp
public OnHostLocationRemoved(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String uri, System.String path, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String uri, System.String path, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String uri, System.String path) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String uri, System.String path);
```


