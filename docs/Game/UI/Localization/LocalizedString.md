# Game.UI.Localization.LocalizedString

**Assembly:** `Game`  
**Namespace:** `Game.UI.Localization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.UI.Localization.ILocElement`, `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.Localization.LocalizedString>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly System.String <id>k__BackingField`  
- `private readonly System.String <value>k__BackingField`  
- `private readonly System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> <args>k__BackingField`  

## Properties

- `public System.String id { get }`  
- `public System.String value { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args { get }`  
- `public System.Boolean isEmpty { get }`  

## Constructors

- `public LocalizedString(System.String id, System.String value, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args)`  

## Methods

- `private static ArgsEqual(System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> a, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> b) : System.Boolean`  
- `public Equals(Game.UI.Localization.LocalizedString other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public static Id(System.String id) : Game.UI.Localization.LocalizedString`  
- `public static IdWithFallback(System.String id, System.String value) : Game.UI.Localization.LocalizedString`  
- `public static Value(System.String value) : Game.UI.Localization.LocalizedString`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

