# Game.UI.Editor.TypePickerPanel+SelectCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class SelectCallback : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public SelectCallback(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.Type type, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.Type type);
}
```


## Constructors

- `public SelectCallback(System.Object object, System.IntPtr method)`  

```csharp
public SelectCallback(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.Type type, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.Type type, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.Type type) : System.Void`  

```csharp
public virtual System.Void Invoke(System.Type type);
```


