# Colossal.UI.Binding.BindingBase

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IDebugBinding`  

## Fields

- `private readonly System.String <group>k__BackingField`  
- `private readonly System.String <name>k__BackingField`  
- `private readonly System.String <path>k__BackingField`  
- `private cohtml.Net.View <view>k__BackingField`  
- `protected static Colossal.Logging.ILog log`  

## Properties

- `public System.String group { get }`  
- `public System.String name { get }`  
- `public System.String path { get }`  
- `public Colossal.UI.Binding.DebugBindingType debugType { get }`  
- `protected cohtml.Net.View view { protected get; private set }`  
- `public System.Boolean attached { get }`  

## Constructors

- `protected BindingBase(System.String group, System.String name)`  

## Methods

- `public virtual Attach(cohtml.Net.View view) : System.Void`  
- `public virtual Detach() : System.Void`  
- `public virtual ToString() : System.String`  

