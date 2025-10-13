# Colossal.OdinSerializer.Utilities.WeakValueGetter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class WeakValueGetter : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public WeakValueGetter(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Object& instance, System.AsyncCallback callback, System.Object object);
    public virtual System.Object EndInvoke(System.Object& instance, System.IAsyncResult result);
    public virtual System.Object Invoke(System.Object& instance);
}
```


## Constructors

- `public WeakValueGetter(System.Object object, System.IntPtr method)`  

```csharp
public WeakValueGetter(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Object& instance, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Object& instance, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.Object& instance, System.IAsyncResult result) : System.Object`  

```csharp
public virtual System.Object EndInvoke(System.Object& instance, System.IAsyncResult result);
```

- `public virtual Invoke(System.Object& instance) : System.Object`  

```csharp
public virtual System.Object Invoke(System.Object& instance);
```


