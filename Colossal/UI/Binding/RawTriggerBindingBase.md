# Colossal.UI.Binding.RawTriggerBindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `Colossal.UI.Binding.BindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public abstract class RawTriggerBindingBase : Colossal.UI.Binding.BindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    private cohtml.Net.BoundEventHandle m_Handle;
    private System.Boolean <active>k__BackingField;
    private readonly Colossal.UI.Binding.JsonReader <jsonReader>k__BackingField;

    public System.Boolean active { get; set; }
    protected Colossal.UI.Binding.JsonReader jsonReader { protected get; }
    public Colossal.UI.Binding.DebugBindingType debugType { get; }

    protected RawTriggerBindingBase(System.String group, System.String name);

    public virtual System.Void Attach(cohtml.Net.View attachView);
    private System.Void BaseCallback();
    protected abstract System.Void Callback();
    public virtual System.Void Detach();
}
```


## Fields

- `private cohtml.Net.BoundEventHandle m_Handle`  

```csharp
private cohtml.Net.BoundEventHandle m_Handle;
```

- `private System.Boolean <active>k__BackingField`  

```csharp
private System.Boolean <active>k__BackingField;
```

- `private readonly Colossal.UI.Binding.JsonReader <jsonReader>k__BackingField`  

```csharp
private readonly Colossal.UI.Binding.JsonReader <jsonReader>k__BackingField;
```


## Properties

- `public System.Boolean active { get; set }`  

```csharp
public System.Boolean active { get; set; }
```

- `protected Colossal.UI.Binding.JsonReader jsonReader { protected get }`  

```csharp
protected Colossal.UI.Binding.JsonReader jsonReader { protected get; }
```

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

```csharp
public Colossal.UI.Binding.DebugBindingType debugType { get; }
```


## Constructors

- `protected RawTriggerBindingBase(System.String group, System.String name)`  

```csharp
protected RawTriggerBindingBase(System.String group, System.String name);
```


## Methods

- `public virtual Attach(cohtml.Net.View attachView) : System.Void`  

```csharp
public virtual System.Void Attach(cohtml.Net.View attachView);
```

- `private BaseCallback() : System.Void`  

```csharp
private System.Void BaseCallback();
```

- `protected abstract Callback() : System.Void`  

```csharp
protected abstract System.Void Callback();
```

- `public virtual Detach() : System.Void`  

```csharp
public virtual System.Void Detach();
```


