# PDX.SDK.Contracts.Events.IEventHub

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Events`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IEventHub : System.IDisposable
{
    public abstract System.Boolean IsSubscribed(System.Guid token);
    public abstract System.Guid Subscribe<T>(System.Action<T> action);
    public abstract System.Guid Subscribe<T>(System.Action<T> action, System.TimeSpan throttleBy);
    public abstract System.Void Unsubscribe(System.Guid token);
}
```


## Methods

- `public abstract IsSubscribed(System.Guid token) : System.Boolean`  

```csharp
public abstract System.Boolean IsSubscribed(System.Guid token);
```

- `public abstract Subscribe<T>(System.Action<T> action) : System.Guid`  

```csharp
public abstract System.Guid Subscribe<T>(System.Action<T> action);
```

- `public abstract Subscribe<T>(System.Action<T> action, System.TimeSpan throttleBy) : System.Guid`  

```csharp
public abstract System.Guid Subscribe<T>(System.Action<T> action, System.TimeSpan throttleBy);
```

- `public abstract Unsubscribe(System.Guid token) : System.Void`  

```csharp
public abstract System.Void Unsubscribe(System.Guid token);
```


