# Game.UI.Widgets.PathSegment

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`, `System.IEquatable<Game.UI.Widgets.PathSegment>`  

## Code

```csharp
public sealed struct PathSegment : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable, System.IEquatable<Game.UI.Widgets.PathSegment>
{
    public System.String m_Key;
    public System.Int32 m_Index;

    public static Game.UI.Widgets.PathSegment Empty { get; }

    public PathSegment(System.String key);
    public PathSegment(System.Int32 index);

    public System.Boolean Equals(Game.UI.Widgets.PathSegment other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public virtual System.String ToString();
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public System.String m_Key`  

```csharp
public System.String m_Key;
```

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Properties

- `public static Game.UI.Widgets.PathSegment Empty { get }`  

```csharp
public static Game.UI.Widgets.PathSegment Empty { get; }
```


## Constructors

- `public PathSegment(System.String key)`  

```csharp
public PathSegment(System.String key);
```

- `public PathSegment(System.Int32 index)`  

```csharp
public PathSegment(System.Int32 index);
```


## Methods

- `public Equals(Game.UI.Widgets.PathSegment other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Widgets.PathSegment other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


