# Game.Simulation.ProductionSpecializationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_BonusQuery`  
- `private Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource> m_ProductionQueue`  
- `private Unity.Jobs.JobHandle m_QueueWriters`  
- `private Game.Simulation.ProductionSpecializationSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public ProductionSpecializationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.ProductionSpecializationSystem+ProducedResource>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.ProductionSpecializationSystem+ProducedResource`  
- `Game.Simulation.ProductionSpecializationSystem+SpecializationJob`  
- `Game.Simulation.ProductionSpecializationSystem+TypeHandle`  

