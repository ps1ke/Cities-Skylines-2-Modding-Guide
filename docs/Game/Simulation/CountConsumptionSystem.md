# Game.Simulation.CountConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_Consumptions`  
- `private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator`  
- `private Unity.Jobs.JobHandle m_ReadDeps`  
- `private Unity.Jobs.JobHandle m_WriteDeps`  
- `private Unity.Jobs.JobHandle m_CopyDeps`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public CountConsumptionSystem()`  

## Methods

- `public AddConsumptionReader(Unity.Jobs.JobHandle deps) : System.Void`  
- `public AddConsumptionWriter(Unity.Jobs.JobHandle deps) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetConsumptionAccumulator(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public GetConsumptions(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.CountConsumptionSystem+CopyConsumptionJob`  

