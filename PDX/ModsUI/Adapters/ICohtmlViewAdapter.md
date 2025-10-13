# PDX.ModsUI.Adapters.ICohtmlViewAdapter

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Adapters`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface ICohtmlViewAdapter : System.IDisposable
{
    public System.Boolean IsActiveAndEnabled { get; }

    public abstract System.Void AddHostLocation(System.String key, System.Collections.Generic.List<System.String> value);
    public abstract cohtml.Net.BoundEventHandle BindCall(System.String callName, System.Delegate handler);
    public abstract System.Void Disable();
    public abstract System.Void Enable();
    public abstract cohtml.Net.BoundEventHandle RegisterForEvent(System.String callName, System.Delegate handler);
    public abstract System.Void Reload();
    public abstract System.Void RemoveHostLocation(System.String key);
    public abstract System.Void TriggerEvent<T>(System.String eventName, T message);
    public abstract System.Void UnbindCall(cohtml.Net.BoundEventHandle boundEventHandle);
    public abstract System.Void UnregisterFromEvent(cohtml.Net.BoundEventHandle boundEventHandle);
}
```


## Properties

- `public System.Boolean IsActiveAndEnabled { get }`  

```csharp
public System.Boolean IsActiveAndEnabled { get; }
```


## Methods

- `public abstract AddHostLocation(System.String key, System.Collections.Generic.List<System.String> value) : System.Void`  

```csharp
public abstract System.Void AddHostLocation(System.String key, System.Collections.Generic.List<System.String> value);
```

- `public abstract BindCall(System.String callName, System.Delegate handler) : cohtml.Net.BoundEventHandle`  

```csharp
public abstract cohtml.Net.BoundEventHandle BindCall(System.String callName, System.Delegate handler);
```

- `public abstract Disable() : System.Void`  

```csharp
public abstract System.Void Disable();
```

- `public abstract Enable() : System.Void`  

```csharp
public abstract System.Void Enable();
```

- `public abstract RegisterForEvent(System.String callName, System.Delegate handler) : cohtml.Net.BoundEventHandle`  

```csharp
public abstract cohtml.Net.BoundEventHandle RegisterForEvent(System.String callName, System.Delegate handler);
```

- `public abstract Reload() : System.Void`  

```csharp
public abstract System.Void Reload();
```

- `public abstract RemoveHostLocation(System.String key) : System.Void`  

```csharp
public abstract System.Void RemoveHostLocation(System.String key);
```

- `public abstract TriggerEvent<T>(System.String eventName, T message) : System.Void`  

```csharp
public abstract System.Void TriggerEvent<T>(System.String eventName, T message);
```

- `public abstract UnbindCall(cohtml.Net.BoundEventHandle boundEventHandle) : System.Void`  

```csharp
public abstract System.Void UnbindCall(cohtml.Net.BoundEventHandle boundEventHandle);
```

- `public abstract UnregisterFromEvent(cohtml.Net.BoundEventHandle boundEventHandle) : System.Void`  

```csharp
public abstract System.Void UnregisterFromEvent(cohtml.Net.BoundEventHandle boundEventHandle);
```


## Events

- `ReadyForBindings` : `System.Action`  

```csharp
public event System.Action ReadyForBindings;
```


