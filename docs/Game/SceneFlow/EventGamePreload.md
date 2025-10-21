# Game.SceneFlow.GameManager+EventGamePreload

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class EventGamePreload : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public EventGamePreload(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
}
```


## Constructors

- `public EventGamePreload(System.Object object, System.IntPtr method)`  

```csharp
public EventGamePreload(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```


