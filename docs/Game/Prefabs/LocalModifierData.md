# Game.Prefabs.LocalModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Game.Buildings.LocalModifierType m_Type`  
- `public Game.Prefabs.ModifierValueMode m_Mode`  
- `public Game.Buildings.ModifierRadiusCombineMode m_RadiusCombineMode`  
- `public Colossal.Mathematics.Bounds1 m_Delta`  
- `public Colossal.Mathematics.Bounds1 m_Radius`  

## Constructors

- `public LocalModifierData(Game.Buildings.LocalModifierType type, Game.Prefabs.ModifierValueMode mode, Game.Buildings.ModifierRadiusCombineMode radiusMode, Colossal.Mathematics.Bounds1 delta, Colossal.Mathematics.Bounds1 radius)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

