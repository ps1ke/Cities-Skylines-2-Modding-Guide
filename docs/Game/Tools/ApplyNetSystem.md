# Game.Tools.ApplyNetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.ComponentTypeSet m_ApplyCreatedTypes`  
- `private Unity.Entities.ComponentTypeSet m_ApplyUpdatedTypes`  
- `private Unity.Entities.ComponentTypeSet m_ApplyDeletedTypes`  
- `private Game.Tools.ApplyNetSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ApplyNetSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.ApplyNetSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyNetSystem+FixConnectedEdgesJob`  
- `Game.Tools.ApplyNetSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyNetSystem+TypeHandle`  

