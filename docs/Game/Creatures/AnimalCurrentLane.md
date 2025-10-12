# Game.Creatures.AnimalCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Entities.Entity m_NextLane`  
- `public Unity.Entities.Entity m_QueueEntity`  
- `public Colossal.Mathematics.Sphere3 m_QueueArea`  
- `public Unity.Mathematics.float2 m_CurvePosition`  
- `public Unity.Mathematics.float2 m_NextPosition`  
- `public Game.Creatures.CreatureLaneFlags m_Flags`  
- `public Game.Creatures.CreatureLaneFlags m_NextFlags`  
- `public System.Single m_LanePosition`  

## Constructors

- `public AnimalCurrentLane(Unity.Entities.Entity lane, System.Single curvePosition, Game.Creatures.CreatureLaneFlags flags)`  
- `public AnimalCurrentLane(Game.Creatures.CreatureLaneFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

