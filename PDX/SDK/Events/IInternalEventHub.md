# PDX.SDK.Events.IInternalEventHub

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Events`  

**Type:** interface abstract public  

**Implements:** `PDX.SDK.Contracts.Events.IEventHub`, `System.IDisposable`  

## Code

```csharp
public abstract interface IInternalEventHub : PDX.SDK.Contracts.Events.IEventHub, System.IDisposable
{
    public abstract System.Void ClearSubscriptions();
    public abstract System.Void Publish<T>(T message);
    public abstract System.Void RegisterGlobalErrorHandler(System.Action<System.Guid, System.Exception> onError);
    public abstract System.Void RegisterGlobalHandler(System.Action<System.Type, System.Object> onMessage);
}
```


## Methods

- `public abstract ClearSubscriptions() : System.Void`  

```csharp
public abstract System.Void ClearSubscriptions();
```

- `public abstract Publish<T>(T message) : System.Void`  

```csharp
public abstract System.Void Publish<T>(T message);
```

- `public abstract RegisterGlobalErrorHandler(System.Action<System.Guid, System.Exception> onError) : System.Void`  

```csharp
public abstract System.Void RegisterGlobalErrorHandler(System.Action<System.Guid, System.Exception> onError);
```

- `public abstract RegisterGlobalHandler(System.Action<System.Type, System.Object> onMessage) : System.Void`  

```csharp
public abstract System.Void RegisterGlobalHandler(System.Action<System.Type, System.Object> onMessage);
```


