# Game.Simulation.SpawnableAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  
- `private Unity.Entities.EntityQuery m_SpawnableQuery`  
- `private Unity.Entities.EntityQuery m_EmitterQuery`  
- `private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public SpawnableAmbienceSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.SpawnableAmbienceSystem+GroupAmbienceEffect`  
- `Game.Simulation.SpawnableAmbienceSystem+ApplyAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+EmitterAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+SpawnableAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+TypeHandle`  

