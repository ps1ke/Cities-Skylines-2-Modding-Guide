# Game.UI.Menu.OptionsUISystem+WidgetInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `private System.Int32 <id>k__BackingField`  
- `private Game.UI.Localization.LocalizedString <displayName>k__BackingField`  
- `private System.Boolean <isVisible>k__BackingField`  
- `private System.Boolean <isAdvanced>k__BackingField`  
- `private System.Boolean <searchHidden>k__BackingField`  

## Properties

- `public System.Int32 id { get; set }`  
- `public Game.UI.Localization.LocalizedString displayName { get; set }`  
- `public System.Boolean isVisible { get; set }`  
- `public System.Boolean isAdvanced { get; set }`  
- `public System.Boolean searchHidden { get; set }`  

## Methods

- `public static GetId(System.Int32 page, System.Int32 section, System.Int32 widget) : System.Int32`  
- `public static GetIndices(System.Int32 id, System.Int32& page, System.Int32& section, System.Int32& widget) : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

