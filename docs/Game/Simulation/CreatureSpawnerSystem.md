# Game.Simulation.CreatureSpawnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_SpawnerQuery`  
- `private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes`  
- `private Game.Simulation.CreatureSpawnerSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CreatureSpawnerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CreatureSpawnerSystem+CreatureSpawnerJob`  
- `Game.Simulation.CreatureSpawnerSystem+TypeHandle`  

