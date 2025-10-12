# Game.Simulation.ParkAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_ParkQuery`  
- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  
- `private Game.Simulation.ParkAISystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public ParkAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetMaintenancePriority(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData) : System.Int32`  
- `public static GetModifiedServiceCoverage(Game.Buildings.Park park, Game.Prefabs.ParkData prefabParkData, Game.Prefabs.CoverageData prefabCoverageData, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers) : Game.Buildings.ModifiedServiceCoverage`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ParkAISystem+ParkTickJob`  
- `Game.Simulation.ParkAISystem+TypeHandle`  

