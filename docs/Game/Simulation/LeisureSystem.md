# Game.Simulation.LeisureSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathFindSetupSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Events.AddMeetingSystem m_AddMeetingSystem`  
- `private Unity.Entities.EntityQuery m_LeisureQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  
- `private Unity.Entities.EntityQuery m_ResidentPrefabQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_PopulationQuery`  
- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  
- `private Unity.Collections.NativeQueue<Game.Simulation.LeisureEvent> m_LeisureQueue`  
- `private Game.Simulation.LeisureSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Int32 kLeisureConsumeAmount`  

## Constructors

- `public LeisureSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.LeisureProviderData> tempProviderList, Game.Prefabs.LeisureProviderData providerToAdd) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.LeisureSystem+SpendLeisurejob`  
- `Game.Simulation.LeisureSystem+LeisureJob`  
- `Game.Simulation.LeisureSystem+TypeHandle`  

