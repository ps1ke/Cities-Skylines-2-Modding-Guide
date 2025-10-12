# Game.Simulation.FireSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Objects.SearchSystem m_SearchSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_FireQuery`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  
- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  
- `private Unity.Entities.EntityArchetype m_IgniteEventArchetype`  
- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  
- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  
- `private Game.Simulation.FireSimulationSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public FireSimulationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.FireSimulationSystem+FireSimulationJob`  
- `Game.Simulation.FireSimulationSystem+FireSpreadCheckJob`  
- `Game.Simulation.FireSimulationSystem+TypeHandle`  

