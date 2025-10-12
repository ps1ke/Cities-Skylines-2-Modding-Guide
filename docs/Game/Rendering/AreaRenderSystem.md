# Game.Rendering.AreaRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.AreaBufferSystem m_AreaBufferSystem`  
- `private Game.Rendering.AreaBatchSystem m_AreaBatchSystem`  
- `private Game.Rendering.CityBoundaryMeshSystem m_CityBoundaryMeshSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private System.Int32 m_AreaTriangleBuffer`  
- `private System.Int32 m_AreaBatchBuffer`  
- `private System.Int32 m_AreaBatchColors`  
- `private System.Int32 m_VisibleIndices`  
- `private UnityEngine.Mesh m_AreaMesh`  
- `private UnityEngine.GraphicsBuffer m_ArgsBuffer`  
- `private System.Collections.Generic.List<UnityEngine.GraphicsBuffer+IndirectDrawIndexedArgs> m_ArgsArray`  

## Constructors

- `public AreaRenderSystem()`  

## Methods

- `private static CreateMesh() : UnityEngine.Mesh`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

