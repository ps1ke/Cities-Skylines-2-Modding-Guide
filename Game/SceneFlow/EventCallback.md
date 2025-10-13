# Game.SceneFlow.GameManager+EventCallback

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class EventCallback : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public EventCallback(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke();
}
```


## Constructors

- `public EventCallback(System.Object object, System.IntPtr method)`  

```csharp
public EventCallback(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke() : System.Void`  

```csharp
public virtual System.Void Invoke();
```


