# Game.Simulation.ElectricityRoadConnectionGraphSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_UpdatedEdges`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Game.Simulation.ElectricityRoadConnectionGraphSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ElectricityRoadConnectionGraphSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  
- `public GetEdgeUpdateQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ElectricityRoadConnectionGraphSystem+UpdateRoadConnectionsJob`  
- `Game.Simulation.ElectricityRoadConnectionGraphSystem+UpdateRoadEdgesJob`  
- `Game.Simulation.ElectricityRoadConnectionGraphSystem+TypeHandle`  

