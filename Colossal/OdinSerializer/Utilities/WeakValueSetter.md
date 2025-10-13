# Colossal.OdinSerializer.Utilities.WeakValueSetter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer.Utilities`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class WeakValueSetter : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public WeakValueSetter(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Object& instance, System.Object value, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.Object& instance, System.IAsyncResult result);
    public virtual System.Void Invoke(System.Object& instance, System.Object value);
}
```


## Constructors

- `public WeakValueSetter(System.Object object, System.IntPtr method)`  

```csharp
public WeakValueSetter(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Object& instance, System.Object value, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Object& instance, System.Object value, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.Object& instance, System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.Object& instance, System.IAsyncResult result);
```

- `public virtual Invoke(System.Object& instance, System.Object value) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Object& instance, System.Object value);
```


