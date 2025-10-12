# Game.Prefabs.ObjectBuiltRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  
- `private Unity.Entities.EntityQuery m_ChangedQuery`  
- `private Unity.Entities.EntityQuery m_AllQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private System.Boolean m_Loaded`  
- `private Game.Prefabs.ObjectBuiltRequirementSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ObjectBuiltRequirementSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.ObjectBuiltRequirementSystem+UnlockOnBuildJob`  
- `Game.Prefabs.ObjectBuiltRequirementSystem+TypeHandle`  

