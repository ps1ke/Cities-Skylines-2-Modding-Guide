# Game.Objects.SubElementDeleteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolReadyBarrier m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_DeletedQuery`  
- `private Unity.Entities.EntityQuery m_CreatedQuery`  
- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  
- `private Game.Objects.SubElementDeleteSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SubElementDeleteSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Objects.SubElementDeleteSystem+DeleteSubElementsJob`  
- `Game.Objects.SubElementDeleteSystem+CheckDeletedOwnersJob`  
- `Game.Objects.SubElementDeleteSystem+TypeHandle`  

