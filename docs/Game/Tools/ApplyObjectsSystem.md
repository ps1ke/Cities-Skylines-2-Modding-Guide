# Game.Tools.ApplyObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  
- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  
- `private Unity.Entities.ComponentTypeSet m_TempAnimationTypes`  
- `private Game.Tools.ApplyObjectsSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ApplyObjectsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.ApplyObjectsSystem+PatchTempReferencesJob`  
- `Game.Tools.ApplyObjectsSystem+HandleTempEntitiesJob`  
- `Game.Tools.ApplyObjectsSystem+TypeHandle`  

