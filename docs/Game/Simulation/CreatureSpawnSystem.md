# Game.Simulation.CreatureSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_CreatureQuery`  
- `private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes`  
- `private Game.Simulation.CreatureSpawnSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CreatureSpawnSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CreatureSpawnSystem+SpawnData`  
- `Game.Simulation.CreatureSpawnSystem+SpawnRange`  
- `Game.Simulation.CreatureSpawnSystem+GroupSpawnSourcesJob`  
- `Game.Simulation.CreatureSpawnSystem+TrySpawnCreaturesJob`  
- `Game.Simulation.CreatureSpawnSystem+TypeHandle`  

