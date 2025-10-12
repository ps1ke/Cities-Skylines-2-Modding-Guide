# Colossal.UI.Binding.TriggerBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.BindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Fields

- `private readonly System.Action m_Callback`  
- `private cohtml.Net.BoundEventHandle m_Handle`  

## Properties

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

## Constructors

- `public TriggerBinding(System.String group, System.String name, System.Action callback)`  

## Methods

- `public virtual Attach(cohtml.Net.View view) : System.Void`  
- `private Callback() : System.Void`  
- `public virtual Detach() : System.Void`  

