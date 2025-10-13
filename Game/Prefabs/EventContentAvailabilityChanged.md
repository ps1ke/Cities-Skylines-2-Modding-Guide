# Game.Prefabs.PrefabSystem+EventContentAvailabilityChanged

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class EventContentAvailabilityChanged : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public EventContentAvailabilityChanged(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Game.Prefabs.ContentPrefab contentPrefab, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Game.Prefabs.ContentPrefab contentPrefab);
}
```


## Constructors

- `public EventContentAvailabilityChanged(System.Object object, System.IntPtr method)`  

```csharp
public EventContentAvailabilityChanged(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Game.Prefabs.ContentPrefab contentPrefab, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Game.Prefabs.ContentPrefab contentPrefab, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Game.Prefabs.ContentPrefab contentPrefab) : System.Void`  

```csharp
public virtual System.Void Invoke(Game.Prefabs.ContentPrefab contentPrefab);
```


