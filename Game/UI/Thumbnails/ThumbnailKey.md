# Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey

**Assembly:** `Game`  
**Namespace:** `Game.UI.Thumbnails`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct ThumbnailKey : System.IEquatable<Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey>
{
    private readonly System.String <name>k__BackingField;
    private readonly System.Int32 <width>k__BackingField;
    private readonly System.Int32 <height>k__BackingField;

    public System.String name { get; }
    public System.Int32 width { get; }
    public System.Int32 height { get; }

    public ThumbnailKey(System.String name, System.Int32 width, System.Int32 height);

    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey other);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
```

- `private readonly System.Int32 <width>k__BackingField`  

```csharp
private readonly System.Int32 <width>k__BackingField;
```

- `private readonly System.Int32 <height>k__BackingField`  

```csharp
private readonly System.Int32 <height>k__BackingField;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Int32 width { get }`  

```csharp
public System.Int32 width { get; }
```

- `public System.Int32 height { get }`  

```csharp
public System.Int32 height { get; }
```


## Constructors

- `public ThumbnailKey(System.String name, System.Int32 width, System.Int32 height)`  

```csharp
public ThumbnailKey(System.String name, System.Int32 width, System.Int32 height);
```


## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Thumbnails.ThumbnailCache+ThumbnailKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


