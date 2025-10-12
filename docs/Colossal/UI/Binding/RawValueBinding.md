# Colossal.UI.Binding.RawValueBinding

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.RawEventBindingBase`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`, `Colossal.UI.Binding.IUpdateBinding`  

## Fields

- `private readonly System.String m_PatchEventName`  
- `private readonly System.Action<Colossal.UI.Binding.IJsonWriter> m_WriterDelegate`  

## Properties

- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  

## Constructors

- `public RawValueBinding(System.String group, System.String name, System.Action<Colossal.UI.Binding.IJsonWriter> writerDelegate)`  

## Methods

- `protected virtual OnSubscribe() : System.Void`  
- `public PatchBegin() : Colossal.UI.Binding.IJsonWriter`  
- `public PatchEnd() : System.Void`  
- `public Update() : System.Boolean`  

