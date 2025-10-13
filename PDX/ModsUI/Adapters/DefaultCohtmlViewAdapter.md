# PDX.ModsUI.Adapters.DefaultCohtmlViewAdapter

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.Adapters`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.ModsUI.Adapters.ICohtmlViewAdapter`, `System.IDisposable`  

## Code

```csharp
public class DefaultCohtmlViewAdapter : PDX.ModsUI.Adapters.ICohtmlViewAdapter, System.IDisposable
{
    private cohtml.CohtmlView <CohtmlView>k__BackingField;
    private System.Action ReadyForBindings;

    private cohtml.CohtmlView CohtmlView { private get; private set; }
    private System.Boolean IsAvailable { private get; }
    public System.Boolean IsActiveAndEnabled { get; }

    public DefaultCohtmlViewAdapter(cohtml.CohtmlView cohtmlView);

    public System.Void AddHostLocation(System.String key, System.Collections.Generic.List<System.String> value);
    public cohtml.Net.BoundEventHandle BindCall(System.String callName, System.Delegate handler);
    public System.Void Disable();
    public System.Void Dispose();
    public System.Void Enable();
    private System.Void OnReadyForBindings();
    public cohtml.Net.BoundEventHandle RegisterForEvent(System.String callName, System.Delegate handler);
    public System.Void Reload();
    public System.Void RemoveHostLocation(System.String key);
    public System.Void TriggerEvent<T>(System.String eventName, T message);
    public System.Void UnbindCall(cohtml.Net.BoundEventHandle boundEventHandle);
    public System.Void UnregisterFromEvent(cohtml.Net.BoundEventHandle boundEventHandle);
}
```


## Fields

- `private cohtml.CohtmlView <CohtmlView>k__BackingField`  

```csharp
private cohtml.CohtmlView <CohtmlView>k__BackingField;
```

- `private System.Action ReadyForBindings`  

```csharp
private System.Action ReadyForBindings;
```


## Properties

- `private cohtml.CohtmlView CohtmlView { private get; private set }`  

```csharp
private cohtml.CohtmlView CohtmlView { private get; private set; }
```

- `private System.Boolean IsAvailable { private get }`  

```csharp
private System.Boolean IsAvailable { private get; }
```

- `public System.Boolean IsActiveAndEnabled { get }`  

```csharp
public System.Boolean IsActiveAndEnabled { get; }
```


## Constructors

- `public DefaultCohtmlViewAdapter(cohtml.CohtmlView cohtmlView)`  

```csharp
public DefaultCohtmlViewAdapter(cohtml.CohtmlView cohtmlView);
```


## Methods

- `public AddHostLocation(System.String key, System.Collections.Generic.List<System.String> value) : System.Void`  

```csharp
public System.Void AddHostLocation(System.String key, System.Collections.Generic.List<System.String> value);
```

- `public BindCall(System.String callName, System.Delegate handler) : cohtml.Net.BoundEventHandle`  

```csharp
public cohtml.Net.BoundEventHandle BindCall(System.String callName, System.Delegate handler);
```

- `public Disable() : System.Void`  

```csharp
public System.Void Disable();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Enable() : System.Void`  

```csharp
public System.Void Enable();
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private System.Void OnReadyForBindings();
```

- `public RegisterForEvent(System.String callName, System.Delegate handler) : cohtml.Net.BoundEventHandle`  

```csharp
public cohtml.Net.BoundEventHandle RegisterForEvent(System.String callName, System.Delegate handler);
```

- `public Reload() : System.Void`  

```csharp
public System.Void Reload();
```

- `public RemoveHostLocation(System.String key) : System.Void`  

```csharp
public System.Void RemoveHostLocation(System.String key);
```

- `public TriggerEvent<T>(System.String eventName, T message) : System.Void`  

```csharp
public System.Void TriggerEvent<T>(System.String eventName, T message);
```

- `public UnbindCall(cohtml.Net.BoundEventHandle boundEventHandle) : System.Void`  

```csharp
public System.Void UnbindCall(cohtml.Net.BoundEventHandle boundEventHandle);
```

- `public UnregisterFromEvent(cohtml.Net.BoundEventHandle boundEventHandle) : System.Void`  

```csharp
public System.Void UnregisterFromEvent(cohtml.Net.BoundEventHandle boundEventHandle);
```


## Events

- `ReadyForBindings` : `System.Action`  

```csharp
public event System.Action ReadyForBindings;
```


