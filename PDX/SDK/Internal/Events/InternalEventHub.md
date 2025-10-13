# PDX.SDK.Internal.Events.InternalEventHub

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Internal.Events`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.SDK.Events.IInternalEventHub`, `PDX.SDK.Contracts.Events.IEventHub`, `System.IDisposable`  

## Code

```csharp
public class InternalEventHub : PDX.SDK.Events.IInternalEventHub, PDX.SDK.Contracts.Events.IEventHub, System.IDisposable
{
    private readonly System.Threading.SynchronizationContext _mainThreadSynchronizationContext;
    private readonly Easy.MessageHub.MessageHub _messageHub;

    public InternalEventHub(System.Threading.SynchronizationContext mainThreadSynchronizationContext);

    public System.Void ClearSubscriptions();
    public System.Void Dispose();
    public System.Boolean IsSubscribed(System.Guid token);
    public System.Void Publish<T>(T message);
    public System.Void RegisterGlobalErrorHandler(System.Action<System.Guid, System.Exception> onError);
    public System.Void RegisterGlobalHandler(System.Action<System.Type, System.Object> onMessage);
    public System.Guid Subscribe<T>(System.Action<T> action);
    public System.Guid Subscribe<T>(System.Action<T> action, System.TimeSpan throttleBy);
    public System.Void Unsubscribe(System.Guid token);
}
```


## Fields

- `private readonly System.Threading.SynchronizationContext _mainThreadSynchronizationContext`  

```csharp
private readonly System.Threading.SynchronizationContext _mainThreadSynchronizationContext;
```

- `private readonly Easy.MessageHub.MessageHub _messageHub`  

```csharp
private readonly Easy.MessageHub.MessageHub _messageHub;
```


## Constructors

- `public InternalEventHub(System.Threading.SynchronizationContext mainThreadSynchronizationContext)`  

```csharp
public InternalEventHub(System.Threading.SynchronizationContext mainThreadSynchronizationContext);
```


## Methods

- `public ClearSubscriptions() : System.Void`  

```csharp
public System.Void ClearSubscriptions();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public IsSubscribed(System.Guid token) : System.Boolean`  

```csharp
public System.Boolean IsSubscribed(System.Guid token);
```

- `public Publish<T>(T message) : System.Void`  

```csharp
public System.Void Publish<T>(T message);
```

- `public RegisterGlobalErrorHandler(System.Action<System.Guid, System.Exception> onError) : System.Void`  

```csharp
public System.Void RegisterGlobalErrorHandler(System.Action<System.Guid, System.Exception> onError);
```

- `public RegisterGlobalHandler(System.Action<System.Type, System.Object> onMessage) : System.Void`  

```csharp
public System.Void RegisterGlobalHandler(System.Action<System.Type, System.Object> onMessage);
```

- `public Subscribe<T>(System.Action<T> action) : System.Guid`  

```csharp
public System.Guid Subscribe<T>(System.Action<T> action);
```

- `public Subscribe<T>(System.Action<T> action, System.TimeSpan throttleBy) : System.Guid`  

```csharp
public System.Guid Subscribe<T>(System.Action<T> action, System.TimeSpan throttleBy);
```

- `public Unsubscribe(System.Guid token) : System.Void`  

```csharp
public System.Void Unsubscribe(System.Guid token);
```


## Nested types

- `PDX.SDK.Internal.Events.InternalEventHub+<>c__DisplayClass10_0<T>`  

