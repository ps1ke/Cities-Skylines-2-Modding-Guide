# Game.Tools.ValidationSystem+Components

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_ComponentQuery`  
- `public Unity.Collections.NativeHashMap<Unity.Entities.Entity, Game.Tools.ErrorSeverity> m_ErrorMap`  
- `public Unity.Jobs.JobHandle m_ErrorMapDeps`  
- `private Game.Tools.ValidationSystem+Components+TypeHandle __TypeHandle`  

## Constructors

- `public Components()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.ValidationSystem+Components+UpdateComponentsJob`  
- `Game.Tools.ValidationSystem+Components+TypeHandle`  

