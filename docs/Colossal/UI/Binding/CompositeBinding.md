# Colossal.UI.Binding.CompositeBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`  

## Fields

- `private cohtml.Net.View m_View`  
- `private readonly System.Collections.Generic.List<Colossal.UI.Binding.IBinding> m_Bindings`  
- `private readonly System.Collections.Generic.List<Colossal.UI.Binding.IUpdateBinding> m_UpdateBindings`  
- `protected static readonly Colossal.Logging.ILog log`  

## Properties

- `public System.Boolean attached { get }`  
- `public System.Collections.Generic.IEnumerable<Colossal.UI.Binding.IBinding> bindings { get }`  

## Constructors

- `public CompositeBinding()`  

## Methods

- `public AddBinding(Colossal.UI.Binding.IBinding binding) : System.Void`  
- `public AddUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding) : System.Void`  
- `public virtual Attach(cohtml.Net.View view) : System.Void`  
- `private AttachView(Colossal.UI.Binding.IBinding binding) : System.Void`  
- `public virtual Detach() : System.Void`  
- `private DetachView(Colossal.UI.Binding.IBinding binding) : System.Void`  
- `public DisposeBindings() : System.Void`  
- `public RemoveBinding(Colossal.UI.Binding.IBinding binding) : System.Void`  
- `public RemoveUpdateBinding(Colossal.UI.Binding.IUpdateBinding binding) : System.Void`  
- `public virtual Update() : System.Boolean`  

