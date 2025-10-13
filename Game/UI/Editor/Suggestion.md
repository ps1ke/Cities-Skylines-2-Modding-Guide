# Game.UI.Editor.PopupSearchField+Suggestion

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.Editor.PopupSearchField+Suggestion>`, `System.IEquatable<Game.UI.Editor.PopupSearchField+Suggestion>`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct Suggestion : System.IComparable<Game.UI.Editor.PopupSearchField+Suggestion>, System.IEquatable<Game.UI.Editor.PopupSearchField+Suggestion>, Colossal.UI.Binding.IJsonWritable
{
    private System.String <value>k__BackingField;
    private System.Boolean <favorite>k__BackingField;

    public System.String value { get; set; }
    public System.Boolean favorite { get; set; }

    public Suggestion(System.String value, System.Boolean favorite);

    public System.Int32 CompareTo(Game.UI.Editor.PopupSearchField+Suggestion other);
    public System.Boolean Equals(Game.UI.Editor.PopupSearchField+Suggestion other);
    public virtual System.Boolean Equals(System.Object obj);
    public static Game.UI.Editor.PopupSearchField+Suggestion Favorite(System.String value);
    public virtual System.Int32 GetHashCode();
    public static Game.UI.Editor.PopupSearchField+Suggestion NonFavorite(System.String value);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <value>k__BackingField`  

```csharp
private System.String <value>k__BackingField;
```

- `private System.Boolean <favorite>k__BackingField`  

```csharp
private System.Boolean <favorite>k__BackingField;
```


## Properties

- `public System.String value { get; set }`  

```csharp
public System.String value { get; set; }
```

- `public System.Boolean favorite { get; set }`  

```csharp
public System.Boolean favorite { get; set; }
```


## Constructors

- `public Suggestion(System.String value, System.Boolean favorite)`  

```csharp
public Suggestion(System.String value, System.Boolean favorite);
```


## Methods

- `public CompareTo(Game.UI.Editor.PopupSearchField+Suggestion other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.Editor.PopupSearchField+Suggestion other);
```

- `public Equals(Game.UI.Editor.PopupSearchField+Suggestion other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Editor.PopupSearchField+Suggestion other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public static Favorite(System.String value) : Game.UI.Editor.PopupSearchField+Suggestion`  

```csharp
public static Game.UI.Editor.PopupSearchField+Suggestion Favorite(System.String value);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public static NonFavorite(System.String value) : Game.UI.Editor.PopupSearchField+Suggestion`  

```csharp
public static Game.UI.Editor.PopupSearchField+Suggestion NonFavorite(System.String value);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


