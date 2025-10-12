# Game.Rendering.AreaBatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private UnityEngine.ComputeBuffer m_AreaTriangleBuffer`  
- `private UnityEngine.ComputeBuffer m_AreaColorBuffer`  
- `private System.Collections.Generic.List<Game.Rendering.AreaBatchSystem+ManagedBatchData> m_ManagedBatchData`  
- `private Colossal.Collections.NativeHeapAllocator m_AreaBufferAllocator`  
- `private Unity.Collections.NativeReference<System.Int32> m_AllocationCount`  
- `private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+NativeBatchData> m_NativeBatchData`  
- `private Unity.Collections.NativeList<Game.Rendering.AreaTriangleData> m_AreaTriangleData`  
- `private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+TriangleMetaData> m_TriangleMetaData`  
- `private Unity.Collections.NativeList<Game.Rendering.AreaColorData> m_AreaColorData`  
- `private Unity.Collections.NativeList<Colossal.Collections.NativeHeapBlock> m_UpdatedTriangles`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Jobs.JobHandle m_DataDependencies`  
- `private Unity.Mathematics.float3 m_PrevCameraPosition`  
- `private Unity.Mathematics.float3 m_PrevCameraDirection`  
- `private Unity.Mathematics.float4 m_PrevLodParameters`  
- `private System.Int32 m_AreaParameters`  
- `private System.Int32 m_DecalLayerMask`  
- `private System.Boolean m_Loaded`  
- `private System.Boolean m_ColorsUpdated`  
- `private Game.Rendering.AreaBatchSystem+TypeHandle __TypeHandle`  
- `public static const System.UInt32 AREABUFFER_MEMORY_DEFAULT`  
- `public static const System.UInt32 AREABUFFER_MEMORY_INCREMENT`  

## Constructors

- `public AreaBatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddColorWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public EnabledShadersUpdated() : System.Void`  
- `public GetAreaBatch(System.Int32 index, UnityEngine.ComputeBuffer& buffer, UnityEngine.ComputeBuffer& colors, UnityEngine.GraphicsBuffer& indices, UnityEngine.Material& material, UnityEngine.Bounds& bounds, System.Int32& count, System.Int32& rendererPriority) : System.Boolean`  
- `public GetAreaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  
- `public GetBatchCount() : System.Int32`  
- `public GetColorData(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.AreaColorData>`  
- `private GetLoaded() : System.Boolean`  
- `private static GetTriangleSize() : System.UInt32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdatePrefabs() : System.Void`  

## Nested types

- `Game.Rendering.AreaBatchSystem+ManagedBatchData`  
- `Game.Rendering.AreaBatchSystem+NativeBatchData`  
- `Game.Rendering.AreaBatchSystem+TreeCullingJob1`  
- `Game.Rendering.AreaBatchSystem+TreeCullingJob2`  
- `Game.Rendering.AreaBatchSystem+TreeCullingIterator`  
- `Game.Rendering.AreaBatchSystem+QueryCullingJob`  
- `Game.Rendering.AreaBatchSystem+AreaMetaData`  
- `Game.Rendering.AreaBatchSystem+TriangleMetaData`  
- `Game.Rendering.AreaBatchSystem+TriangleSortData`  
- `Game.Rendering.AreaBatchSystem+CullingAction`  
- `Game.Rendering.AreaBatchSystem+AllocationAction`  
- `Game.Rendering.AreaBatchSystem+CullingActionJob`  
- `Game.Rendering.AreaBatchSystem+BatchAllocationJob`  
- `Game.Rendering.AreaBatchSystem+TriangleUpdateJob`  
- `Game.Rendering.AreaBatchSystem+VisibleUpdateJob`  
- `Game.Rendering.AreaBatchSystem+TypeHandle`  

