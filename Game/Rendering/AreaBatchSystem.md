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
[Preserve]
	public AreaBatchSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public AddColorWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddColorWriter(JobHandle jobHandle)
	{
		m_DataDependencies = jobHandle;
	}
```

- `public EnabledShadersUpdated() : System.Void`  

```csharp
public void EnabledShadersUpdated()
	{
		m_DataDependencies.Complete();
		for (int i = 0; i < m_ManagedBatchData.Count; i++)
		{
			ManagedBatchData managedBatchData = m_ManagedBatchData[i];
			ref NativeBatchData reference = ref m_NativeBatchData.ElementAt(i);
			bool flag = m_RenderingSystem.IsShaderEnabled(managedBatchData.m_Material.shader);
			reference.m_VisibleUpdated |= flag != reference.m_IsEnabled;
			reference.m_IsEnabled = flag;
		}
	}
```

- `public GetAreaBatch(System.Int32 index, UnityEngine.ComputeBuffer& buffer, UnityEngine.ComputeBuffer& colors, UnityEngine.GraphicsBuffer& indices, UnityEngine.Material& material, UnityEngine.Bounds& bounds, System.Int32& count, System.Int32& rendererPriority) : System.Boolean`  

```csharp
public unsafe bool GetAreaBatch(int index, out ComputeBuffer buffer, out ComputeBuffer colors, out GraphicsBuffer indices, out Material material, out Bounds bounds, out int count, out int rendererPriority)
	{
		m_DataDependencies.Complete();
		ManagedBatchData managedBatchData = m_ManagedBatchData[index];
		ref NativeBatchData reference = ref m_NativeBatchData.ElementAt(index);
		if (m_AreaTriangleBuffer.count != m_AreaTriangleData.Capacity)
		{
			m_AreaTriangleBuffer.Release();
			m_AreaTriangleBuffer = new ComputeBuffer(m_AreaTriangleData.Capacity, sizeof(AreaTriangleData));
			m_UpdatedTriangles.Clear();
			uint onePastHighestUsedAddress = m_AreaBufferAllocator.OnePastHighestUsedAddress;
			if (onePastHighestUsedAddress != 0)
			{
				m_UpdatedTriangles.Add(new NativeHeapBlock(new UnsafeHeapBlock(0u, onePastHighestUsedAddress)));
			}
		}
		if (m_UpdatedTriangles.Length != 0)
		{
			for (int i = 0; i < m_UpdatedTriangles.Length; i++)
			{
				NativeHeapBlock nativeHeapBlock = m_UpdatedTriangles[i];
				m_AreaTriangleBuffer.SetData(m_AreaTriangleData.AsArray(), (int)nativeHeapBlock.Begin, (int)nativeHeapBlock.Begin, (int)nativeHeapBlock.Length);
			}
			m_UpdatedTriangles.Clear();
		}
		if (m_AreaColorBuffer.count != m_AreaColorData.Capacity)
		{
			m_AreaColorBuffer.Release();
			m_AreaColorBuffer = new ComputeBuffer(m_AreaColorData.Capacity, sizeof(AreaColorData));
		}
		if (m_ColorsUpdated)
		{
			m_ColorsUpdated = false;
			uint onePastHighestUsedAddress2 = m_AreaBufferAllocator.OnePastHighestUsedAddress;
			if (onePastHighestUsedAddress2 != 0)
			{
				m_AreaColorBuffer.SetData(m_AreaColorData.AsArray(), 0, 0, (int)onePastHighestUsedAddress2);
			}
		}
		if (managedBatchData.m_VisibleIndices.count != reference.m_VisibleIndices.Capacity)
		{
			managedBatchData.m_VisibleIndices.Release();
			managedBatchData.m_VisibleIndices = new GraphicsBuffer(GraphicsBuffer.Target.Structured, reference.m_VisibleIndices.Capacity, 4);
		}
		if (reference.m_VisibleIndicesUpdated)
		{
			reference.m_VisibleIndicesUpdated = false;
			if (reference.m_VisibleIndices.Length != 0)
			{
				NativeArray<int> data = NativeArrayUnsafeUtility.ConvertExistingDataToNativeArray<int>(reference.m_VisibleIndices.Ptr, reference.m_VisibleIndices.Length, Allocator.None);
				managedBatchData.m_VisibleIndices.SetData(data, 0, 0, data.Length);
			}
		}
		buffer = m_AreaTriangleBuffer;
		colors = m_AreaColorBuffer;
		indices = managedBatchData.m_VisibleIndices;
		material = managedBatchData.m_Material;
		bounds = RenderingUtils.ToBounds(reference.m_Bounds);
		count = reference.m_VisibleIndices.Length;
		rendererPriority = managedBatchData.m_RendererPriority;
		return count != 0;
	}
```

- `public GetAreaStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public void GetAreaStats(out uint allocatedSize, out uint bufferSize, out uint count)
	{
		m_DataDependencies.Complete();
		allocatedSize = m_AreaBufferAllocator.UsedSpace * GetTriangleSize();
		bufferSize = m_AreaBufferAllocator.Size * GetTriangleSize();
		count = (uint)m_AllocationCount.Value;
	}
```

- `public GetBatchCount() : System.Int32`  

```csharp
public int GetBatchCount()
	{
		return m_ManagedBatchData.Count;
	}
```

- `public GetColorData(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.AreaColorData>`  

```csharp
public NativeList<AreaColorData> GetColorData(out JobHandle dependencies)
	{
		m_ColorsUpdated = true;
		dependencies = m_DataDependencies;
		return m_AreaColorData;
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `private static GetTriangleSize() : System.UInt32`  

```csharp
private unsafe static uint GetTriangleSize()
	{
		return (uint)(sizeof(AreaTriangleData) + sizeof(AreaColorData));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected unsafe override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_BatchDataSystem = base.World.GetOrCreateSystemManaged<BatchDataSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Batch>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<RenderedAreaData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ManagedBatchData = new List<ManagedBatchData>();
		m_AreaBufferAllocator = new NativeHeapAllocator(4194304 / GetTriangleSize(), 1u, Allocator.Persistent);
		m_AllocationCount = new NativeReference<int>(0, Allocator.Persistent);
		m_NativeBatchData = new NativeList<NativeBatchData>(Allocator.Persistent);
		m_AreaTriangleData = new NativeList<AreaTriangleData>(Allocator.Persistent);
		m_TriangleMetaData = new NativeList<TriangleMetaData>(Allocator.Persistent);
		m_AreaColorData = new NativeList<AreaColorData>(Allocator.Persistent);
		m_UpdatedTriangles = new NativeList<NativeHeapBlock>(100, Allocator.Persistent);
		m_AreaTriangleData.ResizeUninitialized((int)m_AreaBufferAllocator.Size);
		m_TriangleMetaData.ResizeUninitialized((int)m_AreaBufferAllocator.Size);
		m_AreaColorData.ResizeUninitialized((int)m_AreaBufferAllocator.Size);
		m_AreaTriangleBuffer = new ComputeBuffer(m_AreaTriangleData.Capacity, sizeof(AreaTriangleData));
		m_AreaColorBuffer = new ComputeBuffer(m_AreaColorData.Capacity, sizeof(AreaColorData));
		m_AreaParameters = Shader.PropertyToID("colossal_AreaParameters");
		m_DecalLayerMask = Shader.PropertyToID("colossal_DecalLayerMask");
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_AreaTriangleBuffer.Release();
		m_AreaColorBuffer.Release();
		for (int i = 0; i < m_ManagedBatchData.Count; i++)
		{
			ManagedBatchData managedBatchData = m_ManagedBatchData[i];
			if (managedBatchData.m_Material != null)
			{
				UnityEngine.Object.Destroy(managedBatchData.m_Material);
			}
			if (managedBatchData.m_VisibleIndices != null)
			{
				managedBatchData.m_VisibleIndices.Release();
			}
		}
		m_DataDependencies.Complete();
		for (int j = 0; j < m_NativeBatchData.Length; j++)
		{
			ref NativeBatchData reference = ref m_NativeBatchData.ElementAt(j);
			if (reference.m_AreaMetaData.IsCreated)
			{
				reference.m_AreaMetaData.Dispose();
			}
			if (reference.m_VisibleIndices.IsCreated)
			{
				reference.m_VisibleIndices.Dispose();
			}
		}
		m_AreaBufferAllocator.Dispose();
		m_AllocationCount.Dispose();
		m_NativeBatchData.Dispose();
		m_AreaTriangleData.Dispose();
		m_TriangleMetaData.Dispose();
		m_AreaColorData.Dispose();
		m_UpdatedTriangles.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		m_DataDependencies.Complete();
		m_UpdatedTriangles.Clear();
		if (!m_PrefabQuery.IsEmptyIgnoreFilter)
		{
			UpdatePrefabs();
		}
		float3 @float = m_PrevCameraPosition;
		float3 float2 = m_PrevCameraDirection;
		float4 float3 = m_PrevLodParameters;
		if (m_CameraUpdateSystem.TryGetLODParameters(out var lodParameters))
		{
			@float = lodParameters.cameraPosition;
			IGameCameraController activeCameraController = m_CameraUpdateSystem.activeCameraController;
			float3 = RenderingUtils.CalculateLodParameters(m_BatchDataSystem.GetLevelOfDetail(m_RenderingSystem.frameLod, activeCameraController), lodParameters);
			float2 = m_CameraUpdateSystem.activeViewer.forward;
		}
		BoundsMask visibleMask = BoundsMask.NormalLayers;
		BoundsMask prevVisibleMask = BoundsMask.NormalLayers;
		if (loaded)
		{
			m_PrevCameraPosition = @float;
			m_PrevCameraDirection = float2;
			m_PrevLodParameters = float3;
			prevVisibleMask = (BoundsMask)0;
		}
		NativeParallelQueue<CullingAction> nativeParallelQueue = new NativeParallelQueue<CullingAction>(Allocator.TempJob);
		NativeQueue<AllocationAction> allocationActions = new NativeQueue<AllocationAction>(Allocator.TempJob);
		NativeArray<int> nodeBuffer = new NativeArray<int>(512, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		NativeArray<int> subDataBuffer = new NativeArray<int>(512, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		JobHandle dependencies;
		TreeCullingJob1 jobData = new TreeCullingJob1
		{
			m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_LodParameters = float3,
			m_PrevLodParameters = m_PrevLodParameters,
			m_CameraPosition = @float,
			m_PrevCameraPosition = m_PrevCameraPosition,
			m_CameraDirection = float2,
			m_PrevCameraDirection = m_PrevCameraDirection,
			m_VisibleMask = visibleMask,
			m_PrevVisibleMask = prevVisibleMask,
			m_NodeBuffer = nodeBuffer,
			m_SubDataBuffer = subDataBuffer,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		TreeCullingJob2 jobData2 = new TreeCullingJob2
		{
			m_AreaSearchTree = jobData.m_AreaSearchTree,
			m_LodParameters = float3,
			m_PrevLodParameters = m_PrevLodParameters,
			m_CameraPosition = @float,
			m_PrevCameraPosition = m_PrevCameraPosition,
			m_CameraDirection = float2,
			m_PrevCameraDirection = m_PrevCameraDirection,
			m_VisibleMask = visibleMask,
			m_PrevVisibleMask = prevVisibleMask,
			m_NodeBuffer = nodeBuffer,
			m_SubDataBuffer = subDataBuffer,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		QueryCullingJob jobData3 = new QueryCullingJob
		{
			m_EntityType = GetEntityTypeHandle(),
			m_BatchType = GetComponentTypeHandle<Batch>(isReadOnly: true),
			m_DeletedType = GetComponentTypeHandle<Deleted>(isReadOnly: true),
			m_PrefabRefType = GetComponentTypeHandle<PrefabRef>(isReadOnly: true),
			m_NodeType = GetBufferTypeHandle<Node>(isReadOnly: true),
			m_TriangleType = GetBufferTypeHandle<Triangle>(isReadOnly: true),
			m_PrefabAreaGeometryData = GetComponentLookup<AreaGeometryData>(isReadOnly: true),
			m_LodParameters = float3,
			m_CameraPosition = @float,
			m_CameraDirection = float2,
			m_VisibleMask = visibleMask,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		CullingActionJob jobData4 = new CullingActionJob
		{
			m_PrefabRefData = GetComponentLookup<PrefabRef>(isReadOnly: true),
			m_PrefabRenderedAreaData = GetComponentLookup<RenderedAreaData>(isReadOnly: true),
			m_Triangles = GetBufferLookup<Triangle>(isReadOnly: true),
			m_CullingActions = nativeParallelQueue.AsReader(),
			m_AllocationActions = allocationActions.AsParallelWriter(),
			m_BatchData = GetComponentLookup<Batch>(),
			m_TriangleMetaData = m_TriangleMetaData
		};
		BatchAllocationJob jobData5 = new BatchAllocationJob
		{
			m_BatchData = GetComponentLookup<Batch>(),
			m_NativeBatchData = m_NativeBatchData,
			m_TriangleMetaData = m_TriangleMetaData,
			m_AreaTriangleData = m_AreaTriangleData,
			m_AreaColorData = m_AreaColorData,
			m_UpdatedTriangles = m_UpdatedTriangles,
			m_AllocationActions = allocationActions,
			m_AreaBufferAllocator = m_AreaBufferAllocator,
			m_AllocationCount = m_AllocationCount
		};
		TriangleUpdateJob jobData6 = new TriangleUpdateJob
		{
			m_AreaData = GetComponentLookup<Area>(isReadOnly: true),
			m_OwnerData = GetComponentLookup<Owner>(isReadOnly: true),
			m_TransformData = GetComponentLookup<Game.Objects.Transform>(isReadOnly: true),
			m_PrefabRefData = GetComponentLookup<PrefabRef>(isReadOnly: true),
			m_PrefabRenderedAreaData = GetComponentLookup<RenderedAreaData>(isReadOnly: true),
			m_Nodes = GetBufferLookup<Node>(isReadOnly: true),
			m_Triangles = GetBufferLookup<Triangle>(isReadOnly: true),
			m_Expands = GetBufferLookup<Expand>(isReadOnly: true),
			m_CullingActions = nativeParallelQueue.AsReader(),
			m_BatchData = GetComponentLookup<Batch>(),
			m_TriangleMetaData = m_TriangleMetaData,
			m_AreaTriangleData = m_AreaTriangleData,
			m_NativeBatchData = m_NativeBatchData
		};
		VisibleUpdateJob jobData7 = new VisibleUpdateJob
		{
			m_NativeBatchData = m_NativeBatchData
		};
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(dependsOn: IJobExtensions.Schedule(jobData, dependencies), jobData: jobData2, arrayLength: nodeBuffer.Length, innerloopBatchCount: 1);
		JobHandle dependsOn = IJobParallelForExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(jobHandle, JobChunkExtensions.ScheduleParallel(jobData3, m_UpdatedQuery, base.Dependency)), jobData: jobData4, arrayLength: nativeParallelQueue.HashRange, innerloopBatchCount: 1);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData5, dependsOn);
		JobHandle jobHandle3 = IJobParallelForExtensions.Schedule(jobData6, nativeParallelQueue.HashRange, 1, jobHandle2);
		JobHandle dataDependencies = IJobParallelForExtensions.Schedule(jobData7, m_ManagedBatchData.Count, 1, jobHandle3);
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		nativeParallelQueue.Dispose(jobHandle3);
		allocationActions.Dispose(jobHandle2);
		nodeBuffer.Dispose(jobHandle);
		subDataBuffer.Dispose(jobHandle);
		m_PrevCameraPosition = @float;
		m_PrevCameraDirection = float2;
		m_PrevLodParameters = float3;
		base.Dependency = jobHandle3;
		m_DataDependencies = dataDependencies;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_DataDependencies.Complete();
		m_AllocationCount.Value = 0;
		m_AreaBufferAllocator.Clear();
		m_UpdatedTriangles.Clear();
		for (int i = 0; i < m_NativeBatchData.Length; i++)
		{
			ref NativeBatchData reference = ref m_NativeBatchData.ElementAt(i);
			if (reference.m_AreaMetaData.IsCreated)
			{
				reference.m_AreaMetaData.Clear();
			}
			if (reference.m_VisibleIndices.IsCreated)
			{
				reference.m_VisibleIndices.Clear();
			}
		}
		m_Loaded = true;
	}
```

- `private UpdatePrefabs() : System.Void`  

```csharp
private void UpdatePrefabs()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<AreaGeometryData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
				NativeArray<AreaGeometryData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle3);
				if (archetypeChunk.Has(ref typeHandle))
				{
					m_DataDependencies.Complete();
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						Entity entity = nativeArray2[j];
						RenderedAreaData componentData = base.EntityManager.GetComponentData<RenderedAreaData>(entity);
						if (m_ManagedBatchData.Count <= componentData.m_BatchIndex)
						{
							continue;
						}
						ManagedBatchData managedBatchData = m_ManagedBatchData[componentData.m_BatchIndex];
						NativeBatchData nativeBatchData = m_NativeBatchData[componentData.m_BatchIndex];
						if (!(nativeBatchData.m_Prefab != entity))
						{
							if (managedBatchData.m_Material != null)
							{
								UnityEngine.Object.Destroy(managedBatchData.m_Material);
							}
							if (managedBatchData.m_VisibleIndices != null)
							{
								managedBatchData.m_VisibleIndices.Release();
							}
							if (nativeBatchData.m_AreaMetaData.IsCreated)
							{
								nativeBatchData.m_AreaMetaData.Dispose();
							}
							if (nativeBatchData.m_VisibleIndices.IsCreated)
							{
								nativeBatchData.m_VisibleIndices.Dispose();
							}
							if (componentData.m_BatchIndex != m_ManagedBatchData.Count - 1)
							{
								ManagedBatchData value = m_ManagedBatchData[m_ManagedBatchData.Count - 1];
								NativeBatchData value2 = m_NativeBatchData[m_ManagedBatchData.Count - 1];
								RenderedAreaData componentData2 = base.EntityManager.GetComponentData<RenderedAreaData>(value2.m_Prefab);
								componentData2.m_BatchIndex = componentData.m_BatchIndex;
								base.EntityManager.SetComponentData(value2.m_Prefab, componentData2);
								m_ManagedBatchData[componentData.m_BatchIndex] = value;
								m_NativeBatchData[componentData.m_BatchIndex] = value2;
							}
							m_ManagedBatchData.RemoveAt(m_ManagedBatchData.Count - 1);
							m_NativeBatchData.RemoveAt(m_NativeBatchData.Length - 1);
						}
					}
				}
				else
				{
					for (int k = 0; k < nativeArray2.Length; k++)
					{
						Entity entity2 = nativeArray2[k];
						RenderedArea component = m_PrefabSystem.GetPrefab<AreaPrefab>(nativeArray3[k]).GetComponent<RenderedArea>();
						float minNodeDistance = AreaUtils.GetMinNodeDistance(nativeArray4[k].m_Type);
						float num = minNodeDistance * 2f;
						float num2 = math.clamp(component.m_Roundness, 0.01f, 0.99f) * minNodeDistance;
						RenderedAreaData componentData3 = base.EntityManager.GetComponentData<RenderedAreaData>(entity2);
						componentData3.m_HeightOffset = num;
						componentData3.m_ExpandAmount = num2 * 0.5f;
						componentData3.m_BatchIndex = m_ManagedBatchData.Count;
						base.EntityManager.SetComponentData(entity2, componentData3);
						ManagedBatchData managedBatchData2 = new ManagedBatchData();
						managedBatchData2.m_Material = new Material(component.m_Material);
						managedBatchData2.m_Material.name = "Area batch (" + component.m_Material.name + ")";
						managedBatchData2.m_Material.renderQueue = component.m_Material.shader.renderQueue;
						managedBatchData2.m_Material.SetVector(m_AreaParameters, new Vector4(num2, num, 0f, 0f));
						managedBatchData2.m_Material.SetFloat(m_DecalLayerMask, math.asfloat((int)component.m_DecalLayerMask));
						managedBatchData2.m_RendererPriority = component.m_RendererPriority;
						NativeBatchData value3 = new NativeBatchData
						{
							m_AreaMetaData = new UnsafeList<AreaMetaData>(10, Allocator.Persistent),
							m_VisibleIndices = new UnsafeList<int>(100, Allocator.Persistent),
							m_Prefab = entity2,
							m_IsEnabled = m_RenderingSystem.IsShaderEnabled(managedBatchData2.m_Material.shader)
						};
						managedBatchData2.m_VisibleIndices = new GraphicsBuffer(GraphicsBuffer.Target.Structured, value3.m_VisibleIndices.Capacity, 4);
						m_ManagedBatchData.Add(managedBatchData2);
						m_NativeBatchData.Add(in value3);
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
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

