# Game.UI.Localization.LocalizedString

**Assembly:** `Game`  
**Namespace:** `Game.UI.Localization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Game.UI.Localization.ILocElement`, `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.Localization.LocalizedString>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct LocalizedString : Game.UI.Localization.ILocElement, Colossal.UI.Binding.IJsonWritable, System.IEquatable<Game.UI.Localization.LocalizedString>
{
    private readonly System.String <id>k__BackingField;
    private readonly System.String <value>k__BackingField;
    private readonly System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> <args>k__BackingField;

    public System.String id { get; }
    public System.String value { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args { get; }
    public System.Boolean isEmpty { get; }

    public LocalizedString(System.String id, System.String value, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args);

    private static System.Boolean ArgsEqual(System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> a, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> b);
    public System.Boolean Equals(Game.UI.Localization.LocalizedString other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public static Game.UI.Localization.LocalizedString Id(System.String id);
    public static Game.UI.Localization.LocalizedString IdWithFallback(System.String id, System.String value);
    public static Game.UI.Localization.LocalizedString Value(System.String value);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.String <value>k__BackingField`  

```csharp
private readonly System.String <value>k__BackingField;
```

- `private readonly System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> <args>k__BackingField`  

```csharp
private readonly System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> <args>k__BackingField;
```


## Properties

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String value { get }`  

```csharp
public System.String value { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args { get; }
```

- `public System.Boolean isEmpty { get }`  

```csharp
public System.Boolean isEmpty { get; }
```


## Constructors

- `public LocalizedString(System.String id, System.String value, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args)`  

```csharp
public LocalizedString(System.String id, System.String value, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> args);
```


## Methods

- `private static ArgsEqual(System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> a, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> b) : System.Boolean`  

```csharp
private static System.Boolean ArgsEqual(System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> a, System.Collections.Generic.IReadOnlyDictionary<System.String, Game.UI.Localization.ILocElement> b);
```

- `public Equals(Game.UI.Localization.LocalizedString other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Localization.LocalizedString other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public static Id(System.String id) : Game.UI.Localization.LocalizedString`  

```csharp
public static Game.UI.Localization.LocalizedString Id(System.String id);
```

- `public static IdWithFallback(System.String id, System.String value) : Game.UI.Localization.LocalizedString`  

```csharp
public static Game.UI.Localization.LocalizedString IdWithFallback(System.String id, System.String value);
```

- `public static Value(System.String value) : Game.UI.Localization.LocalizedString`  

```csharp
public static Game.UI.Localization.LocalizedString Value(System.String value);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


