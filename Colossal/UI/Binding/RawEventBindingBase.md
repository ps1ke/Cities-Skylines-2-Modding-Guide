# Colossal.UI.Binding.RawEventBindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `Colossal.UI.Binding.EventBindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public abstract class RawEventBindingBase : Colossal.UI.Binding.EventBindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    private readonly Colossal.UI.Binding.JsonWriter <jsonWriter>k__BackingField;

    protected Colossal.UI.Binding.JsonWriter jsonWriter { protected get; }

    protected RawEventBindingBase(System.String group, System.String name);

    public virtual System.Void Attach(cohtml.Net.View view);
    public virtual System.Void Detach();
}
```


## Fields

- `private readonly Colossal.UI.Binding.JsonWriter <jsonWriter>k__BackingField`  

```csharp
private readonly Colossal.UI.Binding.JsonWriter <jsonWriter>k__BackingField;
```


## Properties

- `protected Colossal.UI.Binding.JsonWriter jsonWriter { protected get }`  

```csharp
protected Colossal.UI.Binding.JsonWriter jsonWriter { protected get; }
```


## Constructors

- `protected RawEventBindingBase(System.String group, System.String name)`  

```csharp
protected RawEventBindingBase(System.String group, System.String name);
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


