# Colossal.UI.Binding.TriggerBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.BindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Code

```csharp
public class TriggerBinding : Colossal.UI.Binding.BindingBase, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IDebugBinding
{
    private readonly System.Action m_Callback;
    private cohtml.Net.BoundEventHandle m_Handle;

    public Colossal.UI.Binding.DebugBindingType debugType { get; }

    public TriggerBinding(System.String group, System.String name, System.Action callback);

    public virtual System.Void Attach(cohtml.Net.View view);
    private System.Void Callback();
    public virtual System.Void Detach();
}
```


## Fields

- `private readonly System.Action m_Callback`  

```csharp
private readonly System.Action m_Callback;
```

- `private cohtml.Net.BoundEventHandle m_Handle`  

```csharp
private cohtml.Net.BoundEventHandle m_Handle;
```


## Properties

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

```csharp
public Colossal.UI.Binding.DebugBindingType debugType { get; }
```


## Constructors

- `public TriggerBinding(System.String group, System.String name, System.Action callback)`  

```csharp
public TriggerBinding(System.String group, System.String name, System.Action callback);
```


## Methods

- `public virtual Attach(cohtml.Net.View view) : System.Void`  

```csharp
public virtual System.Void Attach(cohtml.Net.View view);
```

- `private Callback() : System.Void`  

```csharp
private System.Void Callback();
```

- `public virtual Detach() : System.Void`  

```csharp
public virtual System.Void Detach();
```


