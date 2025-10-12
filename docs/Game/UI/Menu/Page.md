# Game.UI.Menu.OptionsUISystem+Page

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private System.Boolean <builtIn>k__BackingField`  
- `private System.Boolean <warning>k__BackingField`  
- `private System.String <id>k__BackingField`  
- `private System.Int32 <index>k__BackingField`  
- `private System.Boolean <beta>k__BackingField`  
- `private System.Func<System.Boolean> <warningGetter>k__BackingField`  
- `private readonly System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> <sections>k__BackingField`  

## Properties

- `internal System.Boolean builtIn { internal get; internal set }`  
- `public System.Boolean warning { get; private set }`  
- `public System.String id { get; set }`  
- `public System.Int32 index { get; set }`  
- `public System.Boolean beta { get; set }`  
- `public System.Func<System.Boolean> warningGetter { get; set }`  
- `public System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Section> sections { get }`  
- `public System.Collections.ObjectModel.ReadOnlyCollection<Game.UI.Menu.OptionsUISystem+Section> visibleSections { get }`  

## Constructors

- `public Page()`  

## Methods

- `public UpdateNameAndDescription(System.Boolean isAdvanced) : System.Boolean`  
- `public UpdateVisibility(System.Boolean isAdvanced) : System.Boolean`  
- `public UpdateWarning(System.Boolean isAdvanced) : System.Boolean`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Menu.OptionsUISystem+Page+<>c`  

