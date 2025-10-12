# Game.Simulation.CommercialSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup`  
- `private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame`  
- `private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CommercialSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CommercialSpawnSystem+SpawnCompanyJob`  
- `Game.Simulation.CommercialSpawnSystem+TypeHandle`  

