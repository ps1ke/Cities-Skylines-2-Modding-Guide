# Game.SceneFlow.GameManager+EventGameSaveLoad

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class EventGameSaveLoad : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public EventGameSaveLoad(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(System.String saveName, System.Boolean start, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(System.String saveName, System.Boolean start);
}
```


## Constructors

- `public EventGameSaveLoad(System.Object object, System.IntPtr method)`  

```csharp
public EventGameSaveLoad(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(System.String saveName, System.Boolean start, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(System.String saveName, System.Boolean start, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(System.String saveName, System.Boolean start) : System.Void`  

```csharp
public virtual System.Void Invoke(System.String saveName, System.Boolean start);
```


