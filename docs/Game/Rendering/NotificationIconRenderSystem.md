# Game.Rendering.NotificationIconRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.NotificationIconBufferSystem m_BufferSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private UnityEngine.Mesh m_Mesh`  
- `private UnityEngine.Material m_Material`  
- `private UnityEngine.ComputeBuffer m_ArgsBuffer`  
- `private UnityEngine.ComputeBuffer m_InstanceBuffer`  
- `private UnityEngine.Texture2DArray m_TextureArray`  
- `private System.UInt32[] m_ArgsArray`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private System.Int32 m_InstanceBufferID`  
- `private System.Boolean m_UpdateBuffer`  
- `private Game.Rendering.NotificationIconRenderSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NotificationIconRenderSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public DisplayDataUpdated() : System.Void`  
- `private GetArgsBuffer() : UnityEngine.ComputeBuffer`  
- `private GetInstanceBuffer(System.Int32 count) : UnityEngine.ComputeBuffer`  
- `private GetMaterial() : UnityEngine.Material`  
- `private GetMesh() : UnityEngine.Mesh`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Render(UnityEngine.Rendering.ScriptableRenderContext context, System.Collections.Generic.List<UnityEngine.Camera> cameras) : System.Void`  

## Nested types

- `Game.Rendering.NotificationIconRenderSystem+TypeHandle`  

