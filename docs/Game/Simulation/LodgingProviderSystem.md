# Game.Simulation.LodgingProviderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityQuery m_ProviderQuery`  
- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  
- `private Game.Simulation.LodgingProviderSystem+TypeHandle __TypeHandle`  
- `private static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public LodgingProviderSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetRoomCount(Unity.Mathematics.int2 lotSize, System.Int32 level, Game.Prefabs.BuildingPropertyData buildingPropertyData) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.LodgingProviderSystem+LodgingProviderJob`  
- `Game.Simulation.LodgingProviderSystem+TypeHandle`  

