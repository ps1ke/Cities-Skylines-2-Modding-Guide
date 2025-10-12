# Game.Rendering.RouteRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.RouteBufferSystem m_RouteBufferSystem`  
- `private Unity.Entities.EntityQuery m_RouteQuery`  
- `private Unity.Entities.EntityQuery m_LivePathQuery`  
- `private Unity.Entities.EntityQuery m_InfomodeQuery`  
- `private UnityEngine.Mesh m_Mesh`  
- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  
- `private System.Collections.Generic.List<System.UInt32> m_ArgsArray`  
- `private System.Int32 m_RouteSegmentBuffer`  
- `private System.Int32 m_RouteColor`  
- `private System.Int32 m_RouteSize`  
- `private Game.Rendering.RouteRenderSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RouteRenderSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private EnsureMesh() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  
- `private ShouldRenderRoutes() : System.Boolean`  

## Nested types

- `Game.Rendering.RouteRenderSystem+TypeHandle`  

