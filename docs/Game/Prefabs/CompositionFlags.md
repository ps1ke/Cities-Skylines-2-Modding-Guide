# Game.Prefabs.CompositionFlags

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`, `System.IEquatable<Game.Prefabs.CompositionFlags>`  

## Fields

- `public Game.Prefabs.CompositionFlags+General m_General`  
- `public Game.Prefabs.CompositionFlags+Side m_Left`  
- `public Game.Prefabs.CompositionFlags+Side m_Right`  
- `private static const Game.Prefabs.CompositionFlags+General NODE_MASK_GENERAL`  
- `private static const Game.Prefabs.CompositionFlags+General OPTION_MASK_GENERAL`  
- `private static const Game.Prefabs.CompositionFlags+Side NODE_MASK_SIDE`  
- `private static const Game.Prefabs.CompositionFlags+Side OPTION_MASK_SIDE`  

## Properties

- `public static Game.Prefabs.CompositionFlags nodeMask { get }`  
- `public static Game.Prefabs.CompositionFlags optionMask { get }`  

## Constructors

- `public CompositionFlags(Game.Prefabs.CompositionFlags+General general, Game.Prefabs.CompositionFlags+Side left, Game.Prefabs.CompositionFlags+Side right)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Prefabs.CompositionFlags other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

## Nested types

- `Game.Prefabs.CompositionFlags+General`  
- `Game.Prefabs.CompositionFlags+Side`  

