# Colossal.UI.Binding.RawTriggerBindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `Colossal.UI.Binding.BindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Fields

- `private cohtml.Net.BoundEventHandle m_Handle`  
- `private System.Boolean <active>k__BackingField`  
- `private readonly Colossal.UI.Binding.JsonReader <jsonReader>k__BackingField`  

## Properties

- `public System.Boolean active { get; set }`  
- `protected Colossal.UI.Binding.JsonReader jsonReader { protected get }`  
- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

## Constructors

- `protected RawTriggerBindingBase(System.String group, System.String name)`  

## Methods

- `public virtual Attach(cohtml.Net.View attachView) : System.Void`  
- `private BaseCallback() : System.Void`  
- `protected abstract Callback() : System.Void`  
- `public virtual Detach() : System.Void`  

