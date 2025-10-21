# Game.UI.Editor.LoadAssetPanel+LoadCallback

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class LoadCallback : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public LoadCallback(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.Hash128 guid, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.Hash128 guid);
}
```


## Constructors

- `public LoadCallback(System.Object object, System.IntPtr method)`  

```csharp
public LoadCallback(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.Hash128 guid, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.Hash128 guid, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.Hash128 guid) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.Hash128 guid);
```


