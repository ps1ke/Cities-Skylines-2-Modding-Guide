# Colossal.OnNotifyProgress

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class OnNotifyProgress : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public OnNotifyProgress(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String name, System.Int32 progress, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String name, System.Int32 progress);
}
```


## Constructors

- `public OnNotifyProgress(System.Object object, System.IntPtr method)`  

```csharp
public OnNotifyProgress(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String name, System.Int32 progress, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String name, System.Int32 progress, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String name, System.Int32 progress) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String name, System.Int32 progress);
```


