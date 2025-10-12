# Game.Creatures.HumanCurrentLane

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Unity.Entities.Entity m_Lane`  
- `public Unity.Entities.Entity m_QueueEntity`  
- `public Colossal.Mathematics.Sphere3 m_QueueArea`  
- `public Unity.Mathematics.float2 m_CurvePosition`  
- `public Game.Creatures.CreatureLaneFlags m_Flags`  
- `public System.Single m_LanePosition`  

## Constructors

- `public HumanCurrentLane(Game.Routes.AccessLane accessLane, Game.Creatures.CreatureLaneFlags flags)`  
- `public HumanCurrentLane(Game.Pathfind.PathElement pathElement, Game.Creatures.CreatureLaneFlags flags)`  
- `public HumanCurrentLane(Game.Creatures.CreatureLaneFlags flags)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

