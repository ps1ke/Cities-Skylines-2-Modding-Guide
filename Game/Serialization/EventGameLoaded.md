# Game.Serialization.LoadGameSystem+EventGameLoaded

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class EventGameLoaded : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public EventGameLoaded(System.Object object, System.IntPtr method);

    public virtual System.IAsyncResult BeginInvoke(Colossal.Serialization.Entities.Context serializationContext, System.AsyncCallback callback, System.Object object);
    public virtual System.Void EndInvoke(System.IAsyncResult result);
    public virtual System.Void Invoke(Colossal.Serialization.Entities.Context serializationContext);
}
```


## Constructors

- `public EventGameLoaded(System.Object object, System.IntPtr method)`  

```csharp
public EventGameLoaded(System.Object object, System.IntPtr method);
```


## Methods

- `public virtual BeginInvoke(Colossal.Serialization.Entities.Context serializationContext, System.AsyncCallback callback, System.Object object) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(Colossal.Serialization.Entities.Context serializationContext, System.AsyncCallback callback, System.Object object);
```

- `public virtual EndInvoke(System.IAsyncResult result) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult result);
```

- `public virtual Invoke(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
public virtual System.Void Invoke(Colossal.Serialization.Entities.Context serializationContext);
```


