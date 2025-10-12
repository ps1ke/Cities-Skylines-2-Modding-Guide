# Game.Tools.OriginalDeletedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Collections.NativeArray<System.Boolean> m_OriginalDeleted`  
- `private Unity.Jobs.JobHandle m_Dependency`  
- `private Game.Tools.OriginalDeletedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public OriginalDeletedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetOriginalDeletedResult(System.Int32 delay) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.OriginalDeletedSystem+OriginalDeletedJob`  
- `Game.Tools.OriginalDeletedSystem+TypeHandle`  

