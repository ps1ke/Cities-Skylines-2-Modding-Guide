# Colossal.UI.Binding.EventBindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `Colossal.UI.Binding.BindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Fields

- `private cohtml.Net.BoundEventHandle m_SubscribeHandle`  
- `private cohtml.Net.BoundEventHandle m_UnsubscribeHandle`  
- `private readonly System.String <updateEventName>k__BackingField`  
- `private System.Int32 <observerCount>k__BackingField`  

## Properties

- `protected System.String updateEventName { protected get }`  
- `public System.Int32 observerCount { get; private set }`  
- `public System.Boolean active { get }`  
- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

## Constructors

- `protected EventBindingBase(System.String group, System.String name)`  

## Methods

- `public virtual Attach(cohtml.Net.View view) : System.Void`  
- `public virtual Detach() : System.Void`  
- `protected virtual OnSubscribe() : System.Void`  
- `protected virtual OnUnsubscribe() : System.Void`  
- `protected virtual ResetObserverCount() : System.Void`  

