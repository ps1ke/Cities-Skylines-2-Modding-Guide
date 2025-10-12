# Game.Prefabs.PrefabID

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Prefabs.PrefabID>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private System.String m_Type`  
- `private System.String m_Name`  

## Constructors

- `public PrefabID(Game.Prefabs.PrefabBase prefab)`  
- `public PrefabID(System.String type, System.String name)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Equals(Game.Prefabs.PrefabID other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetName() : System.String`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public virtual ToString() : System.String`  

