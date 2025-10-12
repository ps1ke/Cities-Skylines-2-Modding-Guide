# Game.UI.Menu.OptionsUISystem+Section

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private readonly Game.UI.Menu.OptionsUISystem+Page <page>k__BackingField`  
- `private System.String <id>k__BackingField`  
- `private System.Int32 <index>k__BackingField`  
- `private System.Boolean <warning>k__BackingField`  
- `private System.Func<System.Boolean> <warningGetter>k__BackingField`  
- `private readonly System.String[] <groupNames>k__BackingField`  
- `private readonly System.Collections.Generic.HashSet<System.String> <groupToShowName>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <groupVisible>k__BackingField`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> <prevGroupVisible>k__BackingField`  
- `private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> <options>k__BackingField`  
- `private System.Boolean <isVisible>k__BackingField`  

## Properties

- `public Game.UI.Menu.OptionsUISystem+Page page { get }`  
- `public System.String id { get; set }`  
- `public System.Int32 index { get; set }`  
- `public System.Boolean warning { get; private set }`  
- `public System.Func<System.Boolean> warningGetter { get; set }`  
- `public System.String[] groupNames { get }`  
- `public System.Collections.Generic.HashSet<System.String> groupToShowName { get }`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> groupVisible { private get; private set }`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Boolean> prevGroupVisible { private get; private set }`  
- `public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Option> options { get }`  
- `public System.Boolean isVisible { get; private set }`  

## Constructors

- `public Section(System.String id, Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.AutomaticSettings+SettingPageData pageData)`  

## Methods

- `public GetItems(System.Boolean isAdvanced) : System.Collections.Generic.List<Game.UI.Widgets.IWidget>`  
- `public UpdateNameAndDescription(System.Boolean isAdvanced) : System.Boolean`  
- `public UpdateVisibility(System.Boolean isAdvanced) : System.Boolean`  
- `public UpdateWarning(System.Boolean isAdvanced) : System.Boolean`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Menu.OptionsUISystem+Section+<>c`  
- `Game.UI.Menu.OptionsUISystem+Section+<>c__DisplayClass43_0`  
- `Game.UI.Menu.OptionsUISystem+Section+<>c__DisplayClass44_0`  

