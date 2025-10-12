# Game.Creatures.AnimalNavigation

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Mathematics.float3 m_TargetPosition`  
- `public Unity.Mathematics.float3 m_TargetDirection`  
- `public System.Single m_MaxSpeed`  
- `public Game.Objects.TransformState m_TransformState`  
- `public System.Byte m_LastActivity`  
- `public System.Byte m_TargetActivity`  

## Constructors

- `public AnimalNavigation(Unity.Mathematics.float3 position)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

