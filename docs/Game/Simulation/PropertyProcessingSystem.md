# Game.Simulation.PropertyProcessingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery`  
- `private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery`  
- `private Unity.Entities.EntityQuery m_PropertyGroupQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  
- `private Unity.Entities.EntityArchetype m_MovedEventArchetype`  
- `private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties`  
- `private Unity.Jobs.JobHandle m_Writers`  
- `private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PropertyProcessingSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  
- `public GetRentActionQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Buildings.RentAction>`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PropertyProcessingSystem+PutPropertyOnMarketJob`  
- `Game.Simulation.PropertyProcessingSystem+PropertyRentJob`  
- `Game.Simulation.PropertyProcessingSystem+TypeHandle`  

