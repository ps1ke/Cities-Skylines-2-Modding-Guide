# Game.Prefabs.StrictObjectBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  
- `private Unity.Entities.EntityQuery m_ChangedQuery`  
- `private Unity.Entities.EntityQuery m_RequirementQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private System.Boolean m_Loaded`  
- `private Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle __TypeHandle`  

## Constructors

- `public StrictObjectBuiltRequirementSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.StrictObjectBuiltRequirementSystem+TrackObjectsJob`  
- `Game.Prefabs.StrictObjectBuiltRequirementSystem+TypeHandle`  

