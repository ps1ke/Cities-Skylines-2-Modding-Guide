# Game.Citizens.CitizenInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_NewCitizenQuery`  
- `private Unity.Entities.EntityQuery m_TimeSettingQuery`  
- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Common.ModificationBarrier5 m_EndFrameBarrier`  
- `private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CitizenInitializeSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Citizens.CitizenInitializeSystem+InitializeCitizenJob`  
- `Game.Citizens.CitizenInitializeSystem+TypeHandle`  

