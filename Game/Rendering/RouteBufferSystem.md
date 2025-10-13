# Game.Rendering.RouteBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteBufferSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
    private Unity.Entities.EntityQuery m_AllRoutesQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData;
    private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData;
    private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices;
    private Unity.Jobs.JobHandle m_BufferDependencies;
    private System.Boolean m_Loaded;
    private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle;

    public RouteBufferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void Clear();
    public System.Void GetBuffer(System.Int32 index, UnityEngine.Material& material, UnityEngine.ComputeBuffer& segmentBuffer, System.Int32& originalRenderQueue, UnityEngine.Bounds& bounds, UnityEngine.Vector4& size);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData;
```

- `private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData;
```

- `private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices`  

```csharp
private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices;
```

- `private Unity.Jobs.JobHandle m_BufferDependencies`  

```csharp
private Unity.Jobs.JobHandle m_BufferDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteBufferSystem()`  

```csharp
[Preserve]
	public RouteBufferSystem()
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

- `private Clear() : System.Void`  

```csharp
private void Clear()
	{
		if (m_ManagedData != null)
		{
			for (int i = 0; i < m_ManagedData.Count; i++)
			{
				m_ManagedData[i].Dispose();
			}
			m_ManagedData.Clear();
		}
		if (m_FreeBufferIndices != null)
		{
			m_FreeBufferIndices.Clear();
		}
		if (m_NativeData.IsCreated)
		{
			m_BufferDependencies.Complete();
			for (int j = 0; j < m_NativeData.Length; j++)
			{
				m_NativeData.ElementAt(j).Dispose();
			}
			m_NativeData.Clear();
		}
	}
```

- `public GetBuffer(System.Int32 index, UnityEngine.Material& material, UnityEngine.ComputeBuffer& segmentBuffer, System.Int32& originalRenderQueue, UnityEngine.Bounds& bounds, UnityEngine.Vector4& size) : System.Void`  

```csharp
public unsafe void GetBuffer(int index, out Material material, out ComputeBuffer segmentBuffer, out int originalRenderQueue, out Bounds bounds, out Vector4 size)
	{
		material = null;
		segmentBuffer = null;
		originalRenderQueue = 0;
		bounds = default(Bounds);
		size = default(Vector4);
		if (m_ManagedData == null || index < 0 || index >= m_ManagedData.Count)
		{
			return;
		}
		m_BufferDependencies.Complete();
		ManagedData managedData = m_ManagedData[index];
		ref NativeData reference = ref m_NativeData.ElementAt(index);
		if (managedData.m_Updated)
		{
			managedData.m_Updated = false;
			if (managedData.m_SegmentBuffer != null && managedData.m_SegmentBuffer.count != reference.m_SegmentData.Length)
			{
				managedData.m_SegmentBuffer.Release();
				managedData.m_SegmentBuffer = null;
			}
			if (reference.m_SegmentData.Length > 0)
			{
				if (managedData.m_SegmentBuffer == null)
				{
					managedData.m_SegmentBuffer = new ComputeBuffer(reference.m_SegmentData.Length, sizeof(SegmentData));
					managedData.m_SegmentBuffer.name = "Route segment buffer (" + managedData.m_Material.name + ")";
				}
				NativeArray<SegmentData> data = NativeArrayUnsafeUtility.ConvertExistingDataToNativeArray<SegmentData>(reference.m_SegmentData.Ptr, reference.m_SegmentData.Length, Allocator.None);
				managedData.m_SegmentBuffer.SetData(data);
			}
			reference.m_SegmentData.Dispose();
		}
		material = managedData.m_Material;
		segmentBuffer = managedData.m_SegmentBuffer;
		originalRenderQueue = managedData.m_OriginalRenderQueue;
		bounds = RenderingUtils.ToBounds(reference.m_Bounds);
		size = managedData.m_Size;
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_UpdatedRoutesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Route>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Common.Event>(),
				ComponentType.ReadOnly<PathUpdated>()
			}
		});
		m_AllRoutesQuery = GetEntityQuery(ComponentType.ReadOnly<Route>());
		m_RouteConfigQuery = GetEntityQuery(ComponentType.ReadOnly<RouteConfigurationData>());
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
		Clear();
		if (m_NativeData.IsCreated)
		{
			m_NativeData.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery entityQuery = (loaded ? m_AllRoutesQuery : m_UpdatedRoutesQuery);
		if (entityQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		RoutePrefab routePrefab = null;
		HashSet<Entity> hashSet = null;
		m_BufferDependencies.Complete();
		NativeArray<ArchetypeChunk> nativeArray = entityQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Created> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Applied> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Applied_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PathUpdated> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<RouteBufferIndex> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_RouteBufferIndex_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentLookup<Game.Routes.Segment> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Owner> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Deleted> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<PathUpdated> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle4);
				if (nativeArray2.Length != 0)
				{
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						PathUpdated pathUpdated = nativeArray2[j];
						if (componentLookup.HasComponent(pathUpdated.m_Owner) && componentLookup2.HasComponent(pathUpdated.m_Owner) && !componentLookup3.HasComponent(pathUpdated.m_Owner))
						{
							if (hashSet == null)
							{
								hashSet = new HashSet<Entity>();
							}
							hashSet.Add(componentLookup2[pathUpdated.m_Owner].m_Owner);
						}
					}
				}
				else if (archetypeChunk.Has(ref typeHandle))
				{
					NativeArray<RouteBufferIndex> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle6);
					if (m_FreeBufferIndices == null)
					{
						m_FreeBufferIndices = new Stack<int>(nativeArray3.Length);
					}
					for (int k = 0; k < nativeArray3.Length; k++)
					{
						RouteBufferIndex value = nativeArray3[k];
						ManagedData managedData = m_ManagedData[value.m_Index];
						ref NativeData reference = ref m_NativeData.ElementAt(value.m_Index);
						managedData.m_Updated = false;
						reference.m_Updated = false;
						m_FreeBufferIndices.Push(value.m_Index);
						value.m_Index = -1;
						nativeArray3[k] = value;
					}
				}
				else if (loaded || (archetypeChunk.Has(ref typeHandle2) && !archetypeChunk.Has(ref typeHandle3)))
				{
					NativeArray<Entity> nativeArray4 = archetypeChunk.GetNativeArray(entityTypeHandle);
					NativeArray<RouteBufferIndex> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle6);
					NativeArray<PrefabRef> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle5);
					if (m_ManagedData == null)
					{
						m_ManagedData = new List<ManagedData>(nativeArray5.Length);
					}
					if (!m_NativeData.IsCreated)
					{
						m_NativeData = new NativeList<NativeData>(nativeArray5.Length, Allocator.Persistent);
					}
					if (hashSet == null)
					{
						hashSet = new HashSet<Entity>();
					}
					for (int l = 0; l < nativeArray5.Length; l++)
					{
						Entity entity = nativeArray4[l];
						RouteBufferIndex value2 = nativeArray5[l];
						PrefabRef refData = nativeArray6[l];
						if (!m_PrefabSystem.TryGetPrefab<RoutePrefab>(refData, out var prefab))
						{
							RouteConfigurationData singleton = m_RouteConfigQuery.GetSingleton<RouteConfigurationData>();
							if (routePrefab != null)
							{
								prefab = routePrefab;
							}
							else if (m_PrefabSystem.TryGetPrefab<RoutePrefab>(singleton.m_MissingRoutePrefab, out prefab))
							{
								routePrefab = prefab;
							}
						}
						if (m_FreeBufferIndices != null && m_FreeBufferIndices.Count > 0)
						{
							value2.m_Index = m_FreeBufferIndices.Pop();
							ManagedData managedData2 = m_ManagedData[value2.m_Index];
							ref NativeData reference2 = ref m_NativeData.ElementAt(value2.m_Index);
							managedData2.Initialize(prefab);
							reference2.Initialize(entity);
						}
						else
						{
							value2.m_Index = m_ManagedData.Count;
							ManagedData managedData3 = new ManagedData();
							NativeData value3 = default(NativeData);
							managedData3.Initialize(prefab);
							value3.Initialize(entity);
							m_ManagedData.Add(managedData3);
							m_NativeData.Add(in value3);
						}
						nativeArray5[l] = value2;
						hashSet.Add(entity);
					}
				}
				else
				{
					NativeArray<Entity> nativeArray7 = archetypeChunk.GetNativeArray(entityTypeHandle);
					if (hashSet == null)
					{
						hashSet = new HashSet<Entity>();
					}
					for (int m = 0; m < nativeArray7.Length; m++)
					{
						hashSet.Add(nativeArray7[m]);
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		if (hashSet == null)
		{
			return;
		}
		foreach (Entity item in hashSet)
		{
			RouteBufferIndex componentData = base.EntityManager.GetComponentData<RouteBufferIndex>(item);
			if (componentData.m_Index >= 0)
			{
				ManagedData managedData4 = m_ManagedData[componentData.m_Index];
				ref NativeData reference3 = ref m_NativeData.ElementAt(componentData.m_Index);
				managedData4.m_Updated = true;
				reference3.m_Updated = true;
				if (!reference3.m_SegmentData.IsCreated)
				{
					reference3.m_SegmentData = new UnsafeList<SegmentData>(0, Allocator.Persistent);
				}
			}
		}
		UpdateBufferJob jobData = new UpdateBufferJob
		{
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathSourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathSource_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LivePathData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_LivePath_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteSegments = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
			m_CurveElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_CurveElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_CurveSources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_CurveSource_RO_BufferLookup, ref base.CheckedStateRef),
			m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_NativeData = m_NativeData
		};
		m_BufferDependencies = IJobParallelForExtensions.Schedule(jobData, m_NativeData.Length, 1, base.Dependency);
		base.Dependency = m_BufferDependencies;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Rendering.RouteBufferSystem+ManagedData`  
- `Game.Rendering.RouteBufferSystem+NativeData`  
- `Game.Rendering.RouteBufferSystem+SegmentData`  
- `Game.Rendering.RouteBufferSystem+CurveKey`  
- `Game.Rendering.RouteBufferSystem+CurveValue`  
- `Game.Rendering.RouteBufferSystem+SourceKey`  
- `Game.Rendering.RouteBufferSystem+UpdateBufferJob`  
- `Game.Rendering.RouteBufferSystem+TypeHandle`  

