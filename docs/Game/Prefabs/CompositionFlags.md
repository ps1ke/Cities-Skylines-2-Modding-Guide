# Game.Prefabs.CompositionFlags

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`, `System.IEquatable<Game.Prefabs.CompositionFlags>`  

## Code

```csharp
public sealed struct CompositionFlags : Colossal.Serialization.Entities.ISerializable, System.IEquatable<Game.Prefabs.CompositionFlags>
{
    public Game.Prefabs.CompositionFlags+General m_General;
    public Game.Prefabs.CompositionFlags+Side m_Left;
    public Game.Prefabs.CompositionFlags+Side m_Right;
    private static const Game.Prefabs.CompositionFlags+General NODE_MASK_GENERAL;
    private static const Game.Prefabs.CompositionFlags+General OPTION_MASK_GENERAL;
    private static const Game.Prefabs.CompositionFlags+Side NODE_MASK_SIDE;
    private static const Game.Prefabs.CompositionFlags+Side OPTION_MASK_SIDE;

    public static Game.Prefabs.CompositionFlags nodeMask { get; }
    public static Game.Prefabs.CompositionFlags optionMask { get; }

    public CompositionFlags(Game.Prefabs.CompositionFlags+General general, Game.Prefabs.CompositionFlags+Side left, Game.Prefabs.CompositionFlags+Side right);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Prefabs.CompositionFlags other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.CompositionFlags+General m_General`  

```csharp
public Game.Prefabs.CompositionFlags+General m_General;
```

- `public Game.Prefabs.CompositionFlags+Side m_Left`  

```csharp
public Game.Prefabs.CompositionFlags+Side m_Left;
```

- `public Game.Prefabs.CompositionFlags+Side m_Right`  

```csharp
public Game.Prefabs.CompositionFlags+Side m_Right;
```

- `private static const Game.Prefabs.CompositionFlags+General NODE_MASK_GENERAL`  

```csharp
private static const Game.Prefabs.CompositionFlags+General NODE_MASK_GENERAL;
```

- `private static const Game.Prefabs.CompositionFlags+General OPTION_MASK_GENERAL`  

```csharp
private static const Game.Prefabs.CompositionFlags+General OPTION_MASK_GENERAL;
```

- `private static const Game.Prefabs.CompositionFlags+Side NODE_MASK_SIDE`  

```csharp
private static const Game.Prefabs.CompositionFlags+Side NODE_MASK_SIDE;
```

- `private static const Game.Prefabs.CompositionFlags+Side OPTION_MASK_SIDE`  

```csharp
private static const Game.Prefabs.CompositionFlags+Side OPTION_MASK_SIDE;
```


## Properties

- `public static Game.Prefabs.CompositionFlags nodeMask { get }`  

```csharp
public static Game.Prefabs.CompositionFlags nodeMask { get; }
```

- `public static Game.Prefabs.CompositionFlags optionMask { get }`  

```csharp
public static Game.Prefabs.CompositionFlags optionMask { get; }
```


## Constructors

- `public CompositionFlags(Game.Prefabs.CompositionFlags+General general, Game.Prefabs.CompositionFlags+Side left, Game.Prefabs.CompositionFlags+Side right)`  

```csharp
public CompositionFlags(Game.Prefabs.CompositionFlags+General general, Game.Prefabs.CompositionFlags+Side left, Game.Prefabs.CompositionFlags+Side right);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Prefabs.CompositionFlags other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Prefabs.CompositionFlags other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


## Nested types

- `Game.Prefabs.CompositionFlags+General`  
- `Game.Prefabs.CompositionFlags+Side`  

