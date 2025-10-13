# Colossal.ProcessWrapper+StringReadEventHandler

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class StringReadEventHandler : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public StringReadEventHandler(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String text, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String text);
}
```


## Constructors

- `public StringReadEventHandler(System.Object object, System.IntPtr method)`  

```csharp
public StringReadEventHandler(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String text, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String text, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String text) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String text);
```


