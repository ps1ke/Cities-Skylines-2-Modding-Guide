# Game.UI.Menu.AutomaticSettings+ManualProperty

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Menu.AutomaticSettings+IProxyProperty`  

## Fields

- `private System.Boolean <canRead>k__BackingField`  
- `private System.Boolean <canWrite>k__BackingField`  
- `private System.String <name>k__BackingField`  
- `private System.Type <propertyType>k__BackingField`  
- `private System.Type <declaringType>k__BackingField`  
- `private System.Action<System.Object, System.Object> <setter>k__BackingField`  
- `private System.Func<System.Object, System.Object> <getter>k__BackingField`  
- `private readonly System.Collections.Generic.List<System.Attribute> <attributes>k__BackingField`  

## Properties

- `public System.Boolean canRead { get; set }`  
- `public System.Boolean canWrite { get; set }`  
- `public System.String name { get; set }`  
- `public System.Type propertyType { get; set }`  
- `public System.Type declaringType { get; set }`  
- `public System.Action<System.Object, System.Object> setter { get; set }`  
- `public System.Func<System.Object, System.Object> getter { get; set }`  
- `public System.Collections.Generic.List<System.Attribute> attributes { get }`  

## Constructors

- `public ManualProperty(System.Type declaringType, System.Type propertyType, System.String name)`  

## Methods

- `public GetAttribute<T>(System.Boolean inherit = False) : T`  
- `public GetAttributes<T>(System.Boolean inherit = False) : System.Collections.Generic.IEnumerable<T>`  
- `public GetValue(System.Object obj) : System.Object`  
- `public HasAttribute<T>(System.Boolean inherit = False) : System.Boolean`  
- `public SetValue(System.Object obj, System.Object value) : System.Void`  
- `public TryGetAttribute<T>(T& attribute, System.Boolean inherit = False) : System.Boolean`  

