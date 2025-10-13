# Game.Rendering.AreaBatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaBatchSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private UnityEngine.ComputeBuffer m_AreaTriangleBuffer;
    private UnityEngine.ComputeBuffer m_AreaColorBuffer;
    private System.Collections.Generic.List<Game.Rendering.AreaBatchSystem+ManagedBatchData> m_ManagedBatchData;
    private Colossal.Collections.NativeHeapAllocator m_AreaBufferAllocator;
    private Unity.Collections.NativeReference<System.Int32> m_AllocationCount;
    private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+NativeBatchData> m_NativeBatchData;
    private Unity.Collections.NativeList<Game.Rendering.AreaTriangleData> m_AreaTriangleData;
    private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+TriangleMetaData> m_TriangleMetaData;
    private Unity.Collections.NativeList<Game.Rendering.AreaColorData> m_AreaColorData;
    private Unity.Collections.NativeList<Colossal.Collections.NativeHeapBlock> m_UpdatedTriangles;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Jobs.JobHandle m_DataDependencies;
    private Unity.Mathematics.float3 m_PrevCameraPosition;
    private Unity.Mathematics.float3 m_PrevCameraDirection;
    private Unity.Mathematics.float4 m_PrevLodParameters;
    private System.Int32 m_AreaParameters;
    private System.Int32 m_DecalLayerMask;
    private System.Boolean m_Loaded;
    private System.Boolean m_ColorsUpdated;
    private Game.Rendering.AreaBatchSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 AREABUFFER_MEMORY_DEFAULT;
    public static const System.UInt32 AREABUFFER_MEMORY_INCREMENT;

    public AreaBatchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddColorWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void EnabledShadersUpdated();
    public System.Boolean GetAreaBatch(System.Int32 index, UnityEngine.ComputeBuffer& buffer, UnityEngine.ComputeBuffer& colors, UnityEngine.GraphicsBuffer& indices, UnityEngine.Material& material, UnityEngine.Bounds& bounds, System.Int32& count, System.Int32& rendererPriority);
    public System.Void GetAreaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
    public System.Int32 GetBatchCount();
    public Unity.Collections.NativeList<Game.Rendering.AreaColorData> GetColorData(Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetLoaded();
    private static System.UInt32 GetTriangleSize();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdatePrefabs();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private UnityEngine.ComputeBuffer m_AreaTriangleBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AreaTriangleBuffer;
```

- `private UnityEngine.ComputeBuffer m_AreaColorBuffer`  

```csharp
private UnityEngine.ComputeBuffer m_AreaColorBuffer;
```

- `private System.Collections.Generic.List<Game.Rendering.AreaBatchSystem+ManagedBatchData> m_ManagedBatchData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.AreaBatchSystem+ManagedBatchData> m_ManagedBatchData;
```

- `private Colossal.Collections.NativeHeapAllocator m_AreaBufferAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_AreaBufferAllocator;
```

- `private Unity.Collections.NativeReference<System.Int32> m_AllocationCount`  

```csharp
private Unity.Collections.NativeReference<System.Int32> m_AllocationCount;
```

- `private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+NativeBatchData> m_NativeBatchData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+NativeBatchData> m_NativeBatchData;
```

- `private Unity.Collections.NativeList<Game.Rendering.AreaTriangleData> m_AreaTriangleData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AreaTriangleData> m_AreaTriangleData;
```

- `private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+TriangleMetaData> m_TriangleMetaData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AreaBatchSystem+TriangleMetaData> m_TriangleMetaData;
```

- `private Unity.Collections.NativeList<Game.Rendering.AreaColorData> m_AreaColorData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.AreaColorData> m_AreaColorData;
```

- `private Unity.Collections.NativeList<Colossal.Collections.NativeHeapBlock> m_UpdatedTriangles`  

```csharp
private Unity.Collections.NativeList<Colossal.Collections.NativeHeapBlock> m_UpdatedTriangles;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Jobs.JobHandle m_DataDependencies`  

```csharp
private Unity.Jobs.JobHandle m_DataDependencies;
```

- `private Unity.Mathematics.float3 m_PrevCameraPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraPosition;
```

- `private Unity.Mathematics.float3 m_PrevCameraDirection`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraDirection;
```

- `private Unity.Mathematics.float4 m_PrevLodParameters`  

```csharp
private Unity.Mathematics.float4 m_PrevLodParameters;
```

- `private System.Int32 m_AreaParameters`  

```csharp
private System.Int32 m_AreaParameters;
```

- `private System.Int32 m_DecalLayerMask`  

```csharp
private System.Int32 m_DecalLayerMask;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Boolean m_ColorsUpdated`  

```csharp
private System.Boolean m_ColorsUpdated;
```

- `private Game.Rendering.AreaBatchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaBatchSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 AREABUFFER_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 AREABUFFER_MEMORY_DEFAULT;
```

- `public static const System.UInt32 AREABUFFER_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 AREABUFFER_MEMORY_INCREMENT;
```


## Constructors

- `public AreaBatchSystem()`  

```csharp
public AreaBatchSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddColorWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddColorWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public EnabledShadersUpdated() : System.Void`  

```csharp
public System.Void EnabledShadersUpdated();
```

- `public GetAreaBatch(System.Int32 index, UnityEngine.ComputeBuffer& buffer, UnityEngine.ComputeBuffer& colors, UnityEngine.GraphicsBuffer& indices, UnityEngine.Material& material, UnityEngine.Bounds& bounds, System.Int32& count, System.Int32& rendererPriority) : System.Boolean`  

```csharp
public System.Boolean GetAreaBatch(System.Int32 index, UnityEngine.ComputeBuffer& buffer, UnityEngine.ComputeBuffer& colors, UnityEngine.GraphicsBuffer& indices, UnityEngine.Material& material, UnityEngine.Bounds& bounds, System.Int32& count, System.Int32& rendererPriority);
```

- `public GetAreaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public System.Void GetAreaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
```

- `public GetBatchCount() : System.Int32`  

```csharp
public System.Int32 GetBatchCount();
```

- `public GetColorData(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.AreaColorData>`  

```csharp
public Unity.Collections.NativeList<Game.Rendering.AreaColorData> GetColorData(Unity.Jobs.JobHandle& dependencies);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `private static GetTriangleSize() : System.UInt32`  

```csharp
private static System.UInt32 GetTriangleSize();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private UpdatePrefabs() : System.Void`  

```csharp
private System.Void UpdatePrefabs();
```


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

