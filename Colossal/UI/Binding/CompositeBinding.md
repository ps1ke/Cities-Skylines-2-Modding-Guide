# Colossal.UI.Binding.CompositeBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Code

```csharp
public class CompositeBinding : Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup
{
    private cohtml.Net.View m_View;
    private readonly System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings;
    private readonly System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings;
    protected static readonly Colossal.Logging.ILog log;

    public System.Boolean attached { get; }
    public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> bindings { get; }

    public CompositeBinding();

    public System.Void AddBinding(Colossal.UI.Binding.IBinding binding);
    public System.Void AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding);
    public virtual System.Void Attach(cohtml.Net.View view);
    private System.Void AttachView(Colossal.UI.Binding.IBinding binding);
    public virtual System.Void Detach();
    private System.Void DetachView(Colossal.UI.Binding.IBinding binding);
    public System.Void DisposeBindings();
    public System.Void RemoveBinding(Colossal.UI.Binding.IBinding binding);
    public System.Void RemoveUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding);
    public virtual System.Boolean Update();
}
```


## Fields

- `private cohtml.Net.View m_View`  

```csharp
private cohtml.Net.View m_View;
```

- `private readonly System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings`  

```csharp
private readonly System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings;
```

- `private readonly System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings`  

```csharp
private readonly System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings;
```

- `protected static readonly Colossal.Logging.ILog log`  

```csharp
protected static readonly Colossal.Logging.ILog log;
```


## Properties

- `public System.Boolean attached { get }`  

```csharp
public System.Boolean attached { get; }
```

- `public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> bindings { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> bindings { get; }
```


## Constructors

- `public CompositeBinding()`  

```csharp
public CompositeBinding();
```


## Methods

- `public AddBinding(Colossal.UI.Binding.IBinding binding) : System.Void`  

```csharp
public System.Void AddBinding(Colossal.UI.Binding.IBinding binding);
```

- `public AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding) : System.Void`  

```csharp
public System.Void AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding);
```

- `public virtual Attach(cohtml.Net.View view) : System.Void`  

```csharp
public virtual System.Void Attach(cohtml.Net.View view);
```

- `private AttachView(Colossal.UI.Binding.IBinding binding) : System.Void`  

```csharp
private System.Void AttachView(Colossal.UI.Binding.IBinding binding);
```

- `public virtual Detach() : System.Void`  

```csharp
public virtual System.Void Detach();
```

- `private DetachView(Colossal.UI.Binding.IBinding binding) : System.Void`  

```csharp
private System.Void DetachView(Colossal.UI.Binding.IBinding binding);
```

- `public DisposeBindings() : System.Void`  

```csharp
public System.Void DisposeBindings();
```

- `public RemoveBinding(Colossal.UI.Binding.IBinding binding) : System.Void`  

```csharp
public System.Void RemoveBinding(Colossal.UI.Binding.IBinding binding);
```

- `public RemoveUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding) : System.Void`  

```csharp
public System.Void RemoveUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding);
```

- `public virtual Update() : System.Boolean`  

```csharp
public virtual System.Boolean Update();
```


