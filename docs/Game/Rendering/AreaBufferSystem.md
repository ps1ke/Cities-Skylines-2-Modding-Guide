# Game.Rendering.AreaBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_SettingsQuery`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.UI.NameSystem m_NameSystem`  
- `private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData`  
- `private Game.Areas.AreaType m_LastSelectionAreaType`  
- `private Unity.Entities.EntityQuery m_SelectionQuery`  
- `private System.Boolean m_Loaded`  
- `private System.Int32 m_AreaParameters`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels`  
- `private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AreaBufferSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetAreaBuffer(Game.Areas.AreaType type, UnityEngine.ComputeBuffer& buffer, UnityEngine.Material& material, UnityEngine.Bounds& bounds) : System.Boolean`  
- `private GetLoaded() : System.Boolean`  
- `public GetNameMaterial(Game.Areas.AreaType type, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  
- `public GetNameMesh(Game.Areas.AreaType type, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  
- `private InitializeAreaData<T>() : Game.Rendering.AreaBufferSystem+AreaTypeData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnDictionaryChanged() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateLabelVertices(Game.Rendering.AreaBufferSystem+AreaTypeData data, System.Boolean isLoaded) : System.Void`  

## Nested types

- `Game.Rendering.AreaBufferSystem+AreaTriangleData`  
- `Game.Rendering.AreaBufferSystem+MaterialData`  
- `Game.Rendering.AreaBufferSystem+AreaTypeData`  
- `Game.Rendering.AreaBufferSystem+ChunkData`  
- `Game.Rendering.AreaBufferSystem+ResetChunkDataJob`  
- `Game.Rendering.AreaBufferSystem+FillMeshDataJob`  
- `Game.Rendering.AreaBufferSystem+CalculateBoundsJob`  
- `Game.Rendering.AreaBufferSystem+LabelVertexData`  
- `Game.Rendering.AreaBufferSystem+FillNameDataJob`  
- `Game.Rendering.AreaBufferSystem+TypeHandle`  

