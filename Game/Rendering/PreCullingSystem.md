# Game.Rendering.PreCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PreCullingSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Common.BoundsMask <visibleMask>k__BackingField;
    private Game.Common.BoundsMask <becameVisible>k__BackingField;
    private Game.Common.BoundsMask <becameHidden>k__BackingField;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_InitializeQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_CullingInfoQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Mathematics.float3 m_PrevCameraPosition;
    private Unity.Mathematics.float3 m_PrevCameraDirection;
    private Unity.Mathematics.float4 m_PrevLodParameters;
    private Game.Common.BoundsMask m_PrevVisibleMask;
    private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags;
    private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries;
    private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries;
    private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries;
    private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
    private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData;
    private Unity.Entities.Entity m_FadeContainer;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Boolean m_ResetPrevious;
    private System.Boolean m_Loaded;
    private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle;

    public Game.Common.BoundsMask visibleMask { get; private set; }
    public Game.Common.BoundsMask becameVisible { get; private set; }
    public Game.Common.BoundsMask becameHidden { get; private set; }

    public PreCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCullingDataReader(Unity.Jobs.JobHandle dependencies);
    public System.Void AddCullingDataWriter(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeList<Game.Rendering.PreCullingData> GetCullingData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private Unity.Entities.EntityQuery GetCullingQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
    public Unity.Entities.Entity GetFadeContainer();
    private System.Boolean GetLoaded();
    private Game.Rendering.PreCullingSystem+QueryFlags GetQueryFlags();
    private Unity.Entities.EntityQuery GetRelativeQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
    private Unity.Entities.EntityQuery GetRemoveQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
    public Unity.Collections.NativeList<Game.Rendering.PreCullingData> GetUpdatedData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Void InitializeCullingData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void ResetCulling();
}
```


## Fields

- `private Game.Common.BoundsMask <visibleMask>k__BackingField`  

```csharp
private Game.Common.BoundsMask <visibleMask>k__BackingField;
```

- `private Game.Common.BoundsMask <becameVisible>k__BackingField`  

```csharp
private Game.Common.BoundsMask <becameVisible>k__BackingField;
```

- `private Game.Common.BoundsMask <becameHidden>k__BackingField`  

```csharp
private Game.Common.BoundsMask <becameHidden>k__BackingField;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_InitializeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InitializeQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_CullingInfoQuery`  

```csharp
private Unity.Entities.EntityQuery m_CullingInfoQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
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

- `private Game.Common.BoundsMask m_PrevVisibleMask`  

```csharp
private Game.Common.BoundsMask m_PrevVisibleMask;
```

- `private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags`  

```csharp
private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries;
```

- `private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
```

- `private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData;
```

- `private Unity.Entities.Entity m_FadeContainer`  

```csharp
private Unity.Entities.Entity m_FadeContainer;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Boolean m_ResetPrevious`  

```csharp
private System.Boolean m_ResetPrevious;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Game.Common.BoundsMask visibleMask { get; private set }`  

```csharp
public Game.Common.BoundsMask visibleMask { get; private set; }
```

- `public Game.Common.BoundsMask becameVisible { get; private set }`  

```csharp
public Game.Common.BoundsMask becameVisible { get; private set; }
```

- `public Game.Common.BoundsMask becameHidden { get; private set }`  

```csharp
public Game.Common.BoundsMask becameHidden { get; private set; }
```


## Constructors

- `public PreCullingSystem()`  

```csharp
[Preserve]
	public PreCullingSystem()
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

- `public AddCullingDataReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddCullingDataReader(JobHandle dependencies)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, dependencies);
	}
```

- `public AddCullingDataWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddCullingDataWriter(JobHandle dependencies)
	{
		m_WriteDependencies = dependencies;
	}
```

- `public GetCullingData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.PreCullingData>`  

```csharp
public NativeList<PreCullingData> GetCullingData(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies));
		return m_CullingData;
	}
```

- `private GetCullingQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  

```csharp
private EntityQuery GetCullingQuery(QueryFlags flags)
	{
		if (!m_CullingQueries.TryGetValue(flags, out var value))
		{
			List<ComponentType> list = new List<ComponentType>
			{
				ComponentType.ReadOnly<Moving>(),
				ComponentType.ReadOnly<Stopped>(),
				ComponentType.ReadOnly<Updated>()
			};
			List<ComponentType> list2 = new List<ComponentType>
			{
				ComponentType.ReadOnly<Relative>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			};
			if ((flags & QueryFlags.Unspawned) == 0)
			{
				list2.Add(ComponentType.ReadOnly<Unspawned>());
			}
			if ((flags & QueryFlags.Zones) != 0)
			{
				list.Add(ComponentType.ReadOnly<Block>());
			}
			else
			{
				list2.Add(ComponentType.ReadOnly<Block>());
			}
			value = GetEntityQuery(new EntityQueryDesc
			{
				All = new ComponentType[1] { ComponentType.ReadWrite<CullingInfo>() },
				Any = list.ToArray(),
				None = list2.ToArray()
			});
			m_CullingQueries.Add(flags, value);
		}
		return value;
	}
```

- `public GetFadeContainer() : Unity.Entities.Entity`  

```csharp
public Entity GetFadeContainer()
	{
		return m_FadeContainer;
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

- `private GetQueryFlags() : Game.Rendering.PreCullingSystem+QueryFlags`  

```csharp
private QueryFlags GetQueryFlags()
	{
		QueryFlags queryFlags = (QueryFlags)0;
		if (m_RenderingSystem.unspawnedVisible)
		{
			queryFlags |= QueryFlags.Unspawned;
		}
		if (m_ToolSystem.activeTool != null && m_ToolSystem.activeTool.requireZones)
		{
			queryFlags |= QueryFlags.Zones;
		}
		return queryFlags;
	}
```

- `private GetRelativeQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  

```csharp
private EntityQuery GetRelativeQuery(QueryFlags flags)
	{
		flags &= QueryFlags.Unspawned;
		if (!m_RelativeQueries.TryGetValue(flags, out var value))
		{
			List<ComponentType> list = new List<ComponentType>
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			};
			if ((flags & QueryFlags.Unspawned) == 0)
			{
				list.Add(ComponentType.ReadOnly<Unspawned>());
			}
			value = GetEntityQuery(new EntityQueryDesc
			{
				All = new ComponentType[2]
				{
					ComponentType.ReadOnly<Relative>(),
					ComponentType.ReadWrite<CullingInfo>()
				},
				None = list.ToArray()
			});
			m_RelativeQueries.Add(flags, value);
		}
		return value;
	}
```

- `private GetRemoveQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  

```csharp
private EntityQuery GetRemoveQuery(QueryFlags flags)
	{
		if (!m_RemoveQueries.TryGetValue(flags, out var value))
		{
			List<ComponentType> list = new List<ComponentType> { ComponentType.ReadOnly<Deleted>() };
			if ((flags & QueryFlags.Zones) != 0)
			{
				list.Add(ComponentType.ReadOnly<Block>());
			}
			if ((flags & QueryFlags.Unspawned) != 0)
			{
				list.Add(ComponentType.ReadOnly<Unspawned>());
			}
			value = GetEntityQuery(new EntityQueryDesc
			{
				All = new ComponentType[1] { ComponentType.ReadWrite<CullingInfo>() },
				Any = list.ToArray()
			});
			m_RemoveQueries.Add(flags, value);
		}
		return value;
	}
```

- `public GetUpdatedData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.PreCullingData>`  

```csharp
public NativeList<PreCullingData> GetUpdatedData(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_WriteDependencies : JobHandle.CombineDependencies(m_WriteDependencies, m_ReadDependencies));
		return m_UpdatedData;
	}
```

- `private InitializeCullingData() : System.Void`  

```csharp
private void InitializeCullingData()
	{
		m_CullingData.Clear();
		ref NativeList<PreCullingData> reference = ref m_CullingData;
		PreCullingData value = new PreCullingData
		{
			m_Entity = m_FadeContainer,
			m_Flags = (PreCullingFlags.PassedCulling | PreCullingFlags.NearCamera | PreCullingFlags.FadeContainer)
		};
		reference.Add(in value);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_UndergroundViewSystem = base.World.GetOrCreateSystemManaged<UndergroundViewSystem>();
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
		m_BatchDataSystem = base.World.GetOrCreateSystemManaged<BatchDataSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_InitializeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<CullingInfo>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_EventQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Common.Event>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<RentersUpdated>(),
				ComponentType.ReadOnly<ColorUpdated>()
			}
		});
		m_CullingInfoQuery = GetEntityQuery(ComponentType.ReadOnly<CullingInfo>(), ComponentType.Exclude<Deleted>());
		m_TempQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadWrite<CullingInfo>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_CullingQueries = new Dictionary<QueryFlags, EntityQuery>();
		m_RelativeQueries = new Dictionary<QueryFlags, EntityQuery>();
		m_RemoveQueries = new Dictionary<QueryFlags, EntityQuery>();
		m_PrevCameraDirection = math.forward();
		m_PrevLodParameters = 1f;
		m_CullingData = new NativeList<PreCullingData>(10000, Allocator.Persistent);
		m_UpdatedData = new NativeList<PreCullingData>(10000, Allocator.Persistent);
		m_FadeContainer = base.EntityManager.CreateEntity(ComponentType.ReadWrite<MeshBatch>(), ComponentType.ReadWrite<FadeBatch>());
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
		m_WriteDependencies.Complete();
		m_ReadDependencies.Complete();
		m_CullingData.Dispose();
		m_UpdatedData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		m_WriteDependencies.Complete();
		m_ReadDependencies.Complete();
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
		BoundsMask boundsMask = BoundsMask.NormalLayers;
		if (m_UndergroundViewSystem.pipelinesOn)
		{
			boundsMask |= BoundsMask.PipelineLayer;
		}
		if (m_UndergroundViewSystem.subPipelinesOn)
		{
			boundsMask |= BoundsMask.SubPipelineLayer;
		}
		if (m_UndergroundViewSystem.waterwaysOn)
		{
			boundsMask |= BoundsMask.WaterwayLayer;
		}
		if (m_RenderingSystem.markersVisible)
		{
			boundsMask |= BoundsMask.Debug;
		}
		if (m_ResetPrevious)
		{
			m_PrevCameraPosition = @float;
			m_PrevCameraDirection = float2;
			m_PrevLodParameters = float3;
			m_PrevVisibleMask = (BoundsMask)0;
			visibleMask = boundsMask;
			becameVisible = boundsMask;
			becameHidden = (BoundsMask)0;
		}
		else
		{
			visibleMask = boundsMask;
			becameVisible = (BoundsMask)((uint)boundsMask & (uint)(ushort)(~(int)m_PrevVisibleMask));
			becameHidden = (BoundsMask)((uint)m_PrevVisibleMask & (uint)(ushort)(~(int)boundsMask));
		}
		int length = m_CullingData.Length;
		NativeParallelQueue<CullingAction> nativeParallelQueue = new NativeParallelQueue<CullingAction>(Allocator.TempJob);
		NativeReference<int> cullingDataIndex = new NativeReference<int>(length, Allocator.TempJob);
		NativeQueue<OverflowAction> overflowActions = new NativeQueue<OverflowAction>(Allocator.TempJob);
		NativeArray<int> nodeBuffer = new NativeArray<int>(1536, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		NativeArray<int> subDataBuffer = new NativeArray<int>(1536, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		TreeCullingJob1 jobData = new TreeCullingJob1
		{
			m_StaticObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_LaneSearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: true, out dependencies3),
			m_LodParameters = float3,
			m_PrevLodParameters = m_PrevLodParameters,
			m_CameraPosition = @float,
			m_PrevCameraPosition = m_PrevCameraPosition,
			m_CameraDirection = float2,
			m_PrevCameraDirection = m_PrevCameraDirection,
			m_VisibleMask = boundsMask,
			m_PrevVisibleMask = m_PrevVisibleMask,
			m_NodeBuffer = nodeBuffer,
			m_SubDataBuffer = subDataBuffer,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		JobHandle jobHandle = new TreeCullingJob2
		{
			m_StaticObjectSearchTree = jobData.m_StaticObjectSearchTree,
			m_NetSearchTree = jobData.m_NetSearchTree,
			m_LaneSearchTree = jobData.m_LaneSearchTree,
			m_LodParameters = float3,
			m_PrevLodParameters = m_PrevLodParameters,
			m_CameraPosition = @float,
			m_PrevCameraPosition = m_PrevCameraPosition,
			m_CameraDirection = float2,
			m_PrevCameraDirection = m_PrevCameraDirection,
			m_VisibleMask = boundsMask,
			m_PrevVisibleMask = m_PrevVisibleMask,
			m_NodeBuffer = nodeBuffer,
			m_SubDataBuffer = subDataBuffer,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		}.Schedule(dependsOn: IJobParallelForExtensions.Schedule(jobData, 3, 1, JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3)), arrayLength: nodeBuffer.Length, innerloopBatchCount: 1);
		JobHandle.ScheduleBatchedJobs();
		m_BatchMeshSystem.CompleteCaching();
		QueryFlags queryFlags = GetQueryFlags();
		InitializeCullingJob jobData2 = new InitializeCullingJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BatchesUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_BatchesUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OverriddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StartNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EndNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Composition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OrphanType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetMarkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Marker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ZoneBlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionMeshRef = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionMeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_UpdateAll = loaded,
			m_UnspawnedVisible = m_RenderingSystem.unspawnedVisible,
			m_DilatedUtilityTypes = m_UndergroundViewSystem.utilityTypes,
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_CullingData = m_CullingData
		};
		EventCullingJob jobData3 = new EventCullingJob
		{
			m_RentersUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RentersUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ColorUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_ColorUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_CullingData = m_CullingData
		};
		QueryCullingJob jobData4 = new QueryCullingJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LodParameters = float3,
			m_CameraPosition = @float,
			m_CameraDirection = float2,
			m_FrameIndex = m_RenderingSystem.frameIndex,
			m_FrameTime = m_RenderingSystem.frameTime,
			m_VisibleMask = boundsMask,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		QueryRemoveJob jobData5 = new QueryRemoveJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AppliedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Applied_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		RelativeCullingJob jobData6 = new RelativeCullingJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentVehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentLookup, ref base.CheckedStateRef),
			m_LodParameters = float3,
			m_CameraPosition = @float,
			m_CameraDirection = float2,
			m_VisibleMask = boundsMask,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		TempCullingJob jobData7 = new TempCullingJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StaticType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Static_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StoppedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentLookup, ref base.CheckedStateRef),
			m_LodParameters = float3,
			m_CameraPosition = @float,
			m_CameraDirection = float2,
			m_VisibleMask = boundsMask,
			m_TerrainHeightData = jobData2.m_TerrainHeightData,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		};
		EntityQuery query = (loaded ? m_CullingInfoQuery : m_InitializeQuery);
		EntityQuery cullingQuery = GetCullingQuery(queryFlags);
		EntityQuery relativeQuery = GetRelativeQuery(queryFlags);
		EntityQuery removeQuery = GetRemoveQuery(m_PrevQueryFlags & ~queryFlags);
		JobHandle dependsOn = JobChunkExtensions.Schedule(dependsOn: JobChunkExtensions.ScheduleParallel(jobData2, query, base.Dependency), jobData: jobData3, query: m_EventQuery);
		JobHandle dependsOn2 = JobChunkExtensions.ScheduleParallel(jobData4, cullingQuery, dependsOn);
		JobHandle dependsOn3 = JobChunkExtensions.ScheduleParallel(jobData5, removeQuery, dependsOn2);
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(dependsOn: JobChunkExtensions.ScheduleParallel(jobData6, relativeQuery, dependsOn3), jobData: jobData7, query: m_TempQuery);
		if (m_ResetPrevious || becameHidden != 0)
		{
			JobHandle job = IJobParallelForExtensions.Schedule(new VerifyVisibleJob
			{
				m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LodParameters = float3,
				m_CameraPosition = @float,
				m_CameraDirection = float2,
				m_VisibleMask = boundsMask,
				m_CullingData = m_CullingData,
				m_ActionQueue = nativeParallelQueue.AsWriter()
			}, length, 16, jobHandle2);
			m_WriteDependencies = JobHandle.CombineDependencies(jobHandle, job);
		}
		else
		{
			m_WriteDependencies = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		CullingActionJob jobData8 = new CullingActionJob
		{
			m_CullingActions = nativeParallelQueue.AsReader(),
			m_OverflowActions = overflowActions.AsParallelWriter(),
			m_CullingInfo = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CullingData = m_CullingData,
			m_CullingDataIndex = cullingDataIndex
		};
		ResizeCullingDataJob jobData9 = new ResizeCullingDataJob
		{
			m_CullingDataIndex = cullingDataIndex,
			m_CullingData = m_CullingData,
			m_UpdatedData = m_UpdatedData,
			m_OverflowActions = overflowActions
		};
		FilterUpdatesJob jobData10 = new FilterUpdatesJob
		{
			m_CreatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Created_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AppliedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Applied_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BatchesUpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_BatchesUpdated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Object_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_ObjectGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Plant_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RelativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Relative_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Extension_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneCondition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimatedData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RO_BufferLookup, ref base.CheckedStateRef),
			m_SkeletonData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RO_BufferLookup, ref base.CheckedStateRef),
			m_EmissiveData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshColorData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_EffectInstances = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferLookup, ref base.CheckedStateRef),
			m_TimerDelta = m_RenderingSystem.lodTimerDelta,
			m_CullingData = m_CullingData,
			m_UpdatedCullingData = m_UpdatedData.AsParallelWriter()
		};
		JobHandle jobHandle3 = IJobParallelForExtensions.Schedule(jobData8, nativeParallelQueue.HashRange, 1, m_WriteDependencies);
		JobHandle jobHandle4 = IJobExtensions.Schedule(jobData9, jobHandle3);
		JobHandle jobHandle5 = jobData10.Schedule(m_CullingData, 16, jobHandle4);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddLaneSearchTreeReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle2);
		nativeParallelQueue.Dispose(jobHandle3);
		cullingDataIndex.Dispose(jobHandle4);
		overflowActions.Dispose(jobHandle4);
		nodeBuffer.Dispose(jobHandle);
		subDataBuffer.Dispose(jobHandle);
		m_PrevCameraPosition = @float;
		m_PrevCameraDirection = float2;
		m_PrevLodParameters = float3;
		m_PrevVisibleMask = boundsMask;
		m_PrevQueryFlags = queryFlags;
		m_ResetPrevious = false;
		m_WriteDependencies = jobHandle5;
		m_ReadDependencies = default(JobHandle);
		base.Dependency = jobHandle5;
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		m_WriteDependencies.Complete();
		m_ReadDependencies.Complete();
		base.EntityManager.GetBuffer<MeshBatch>(m_FadeContainer).Clear();
		base.EntityManager.GetBuffer<FadeBatch>(m_FadeContainer).Clear();
		InitializeCullingData();
		ResetCulling();
		m_Loaded = true;
	}
```

- `public ResetCulling() : System.Void`  

```csharp
public void ResetCulling()
	{
		m_ResetPrevious = true;
	}
```


## Nested types

- `Game.Rendering.PreCullingSystem+QueryFlags`  
- `Game.Rendering.PreCullingSystem+TreeCullingJob1`  
- `Game.Rendering.PreCullingSystem+TreeCullingJob2`  
- `Game.Rendering.PreCullingSystem+TreeCullingIterator`  
- `Game.Rendering.PreCullingSystem+InitializeCullingJob`  
- `Game.Rendering.PreCullingSystem+EventCullingJob`  
- `Game.Rendering.PreCullingSystem+QueryCullingJob`  
- `Game.Rendering.PreCullingSystem+QueryRemoveJob`  
- `Game.Rendering.PreCullingSystem+RelativeCullingJob`  
- `Game.Rendering.PreCullingSystem+TempCullingJob`  
- `Game.Rendering.PreCullingSystem+VerifyVisibleJob`  
- `Game.Rendering.PreCullingSystem+ActionFlags`  
- `Game.Rendering.PreCullingSystem+CullingAction`  
- `Game.Rendering.PreCullingSystem+OverflowAction`  
- `Game.Rendering.PreCullingSystem+CullingActionJob`  
- `Game.Rendering.PreCullingSystem+ResizeCullingDataJob`  
- `Game.Rendering.PreCullingSystem+FilterUpdatesJob`  
- `Game.Rendering.PreCullingSystem+TypeHandle`  

