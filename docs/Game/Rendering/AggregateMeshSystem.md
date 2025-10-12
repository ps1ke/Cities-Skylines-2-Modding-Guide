# Game.Rendering.AggregateMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CreatedPrefabQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedLabelQuery`  
- `private Unity.Entities.EntityQuery m_LabelQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedArrowQuery`  
- `private Unity.Entities.EntityQuery m_ArrowQuery`  
- `private Unity.Entities.EntityQuery m_TempAggregatedQuery`  
- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  
- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.NameSystem m_NameSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData`  
- `private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels`  
- `private System.Int32 m_FaceColor`  
- `private System.Boolean m_TunnelSelectOn`  
- `private System.Boolean m_Loaded`  
- `private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AggregateMeshSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private ClearMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData) : System.Void`  
- `private DestroyMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData) : System.Void`  
- `private FillArrowMeshData(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `private FillNameMeshData(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public GetArrowMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  
- `public GetArrowMaterialCount() : System.Int32`  
- `public GetArrowMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  
- `private GetLoaded() : System.Boolean`  
- `private GetMaterialData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  
- `private GetMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  
- `public GetNameMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  
- `public GetNameMaterialCount() : System.Int32`  
- `public GetNameMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  
- `private InitializePrefabs() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnDictionaryChanged() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateArrowMaterials(System.Boolean isLoaded) : System.Void`  
- `private UpdateArrowPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded) : Unity.Jobs.JobHandle`  
- `private UpdateLabelPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded) : Unity.Jobs.JobHandle`  
- `private UpdateLabelVertices(System.Boolean isLoaded) : System.Void`  
- `private UpdateUndergroundState(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Boolean undergroundOn) : System.Void`  

## Nested types

- `Game.Rendering.AggregateMeshSystem+MaterialData`  
- `Game.Rendering.AggregateMeshSystem+MeshData`  
- `Game.Rendering.AggregateMeshSystem+MaterialUpdate`  
- `Game.Rendering.AggregateMeshSystem+UpdateLabelPositionsJob`  
- `Game.Rendering.AggregateMeshSystem+FillTempMapJob`  
- `Game.Rendering.AggregateMeshSystem+TempValue`  
- `Game.Rendering.AggregateMeshSystem+UpdateArrowPositionsJob`  
- `Game.Rendering.AggregateMeshSystem+LabelVertexData`  
- `Game.Rendering.AggregateMeshSystem+SubMeshData`  
- `Game.Rendering.AggregateMeshSystem+FillNameDataJob`  
- `Game.Rendering.AggregateMeshSystem+ArrowVertexData`  
- `Game.Rendering.AggregateMeshSystem+FillArrowDataJob`  
- `Game.Rendering.AggregateMeshSystem+TypeHandle`  

