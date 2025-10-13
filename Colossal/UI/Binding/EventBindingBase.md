# Colossal.UI.Binding.EventBindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `Colossal.UI.Binding.BindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public abstract class EventBindingBase : Colossal.UI.Binding.BindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    private cohtml.Net.BoundEventHandle m_SubscribeHandle;
    private cohtml.Net.BoundEventHandle m_UnsubscribeHandle;
    private readonly System.String <updateEventName>k__BackingField;
    private System.Int32 <observerCount>k__BackingField;

    protected System.String updateEventName { protected get; }
    public System.Int32 observerCount { get; private set; }
    public System.Boolean active { get; }
    public Colossal.UI.Binding.DebugBindingType debugType { get; }

    protected EventBindingBase(System.String group, System.String name);

    public virtual System.Void Attach(cohtml.Net.View view);
    public virtual System.Void Detach();
    protected virtual System.Void OnSubscribe();
    protected virtual System.Void OnUnsubscribe();
    protected virtual System.Void ResetObserverCount();
}
```


## Fields

- `private cohtml.Net.BoundEventHandle m_SubscribeHandle`  

```csharp
private cohtml.Net.BoundEventHandle m_SubscribeHandle;
```

- `private cohtml.Net.BoundEventHandle m_UnsubscribeHandle`  

```csharp
private cohtml.Net.BoundEventHandle m_UnsubscribeHandle;
```

- `private readonly System.String <updateEventName>k__BackingField`  

```csharp
private readonly System.String <updateEventName>k__BackingField;
```

- `private System.Int32 <observerCount>k__BackingField`  

```csharp
private System.Int32 <observerCount>k__BackingField;
```


## Properties

- `protected System.String updateEventName { protected get }`  

```csharp
protected System.String updateEventName { protected get; }
```

- `public System.Int32 observerCount { get; private set }`  

```csharp
public System.Int32 observerCount { get; private set; }
```

- `public System.Boolean active { get }`  

```csharp
public System.Boolean active { get; }
```

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

```csharp
public Colossal.UI.Binding.DebugBindingType debugType { get; }
```


## Constructors

- `protected EventBindingBase(System.String group, System.String name)`  

```csharp
protected EventBindingBase(System.String group, System.String name);
```


## Methods

- `public virtual Attach(cohtml.Net.View view) : System.Void`  

```csharp
public virtual System.Void Attach(cohtml.Net.View view);
```

- `public virtual Detach() : System.Void`  

```csharp
public virtual System.Void Detach();
```

- `protected virtual OnSubscribe() : System.Void`  

```csharp
protected virtual System.Void OnSubscribe();
```

- `protected virtual OnUnsubscribe() : System.Void`  

```csharp
protected virtual System.Void OnUnsubscribe();
```

- `protected virtual ResetObserverCount() : System.Void`  

```csharp
protected virtual System.Void ResetObserverCount();
```


