# Game.Debug.ObjectDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_ObjectGroup`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Debug.BaseDebugSystem+Option m_GeometryOption`  
- `private Game.Debug.BaseDebugSystem+Option m_MarkerOption`  
- `private Game.Debug.BaseDebugSystem+Option m_PivotOption`  
- `private Game.Debug.BaseDebugSystem+Option m_OutlineOption`  
- `private Game.Debug.BaseDebugSystem+Option m_InterpolatedOption`  
- `private Game.Debug.BaseDebugSystem+Option m_NetConnectionOption`  
- `private Game.Debug.BaseDebugSystem+Option m_GroupConnectionOption`  
- `private Game.Debug.BaseDebugSystem+Option m_DistrictOption`  
- `private Game.Debug.BaseDebugSystem+Option m_LotHeightOption`  
- `private Game.Debug.ObjectDebugSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ObjectDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private DrawObjectGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Debug.ObjectDebugSystem+ObjectGizmoJob`  
- `Game.Debug.ObjectDebugSystem+TypeHandle`  

