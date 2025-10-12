# Game.Simulation.WaterPipeGraphDeleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_DeletedConnectionQuery`  
- `private Unity.Entities.EntityQuery m_DeletedValveNodeQuery`  
- `private Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WaterPipeGraphDeleteSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WaterPipeGraphDeleteSystem+DeleteConnectionsJob`  
- `Game.Simulation.WaterPipeGraphDeleteSystem+DeleteValveNodesJob`  
- `Game.Simulation.WaterPipeGraphDeleteSystem+TypeHandle`  

