# Game.UI.Editor.PopupSearchField+Suggestion

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.Editor.PopupSearchField+Suggestion>`, `System.IEquatable<Game.UI.Editor.PopupSearchField+Suggestion>`, `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `private System.String <value>k__BackingField`  
- `private System.Boolean <favorite>k__BackingField`  

## Properties

- `public System.String value { get; set }`  
- `public System.Boolean favorite { get; set }`  

## Constructors

- `public Suggestion(System.String value, System.Boolean favorite)`  

## Methods

- `public CompareTo(Game.UI.Editor.PopupSearchField+Suggestion other) : System.Int32`  
- `public Equals(Game.UI.Editor.PopupSearchField+Suggestion other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public static Favorite(System.String value) : Game.UI.Editor.PopupSearchField+Suggestion`  
- `public virtual GetHashCode() : System.Int32`  
- `public static NonFavorite(System.String value) : Game.UI.Editor.PopupSearchField+Suggestion`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

