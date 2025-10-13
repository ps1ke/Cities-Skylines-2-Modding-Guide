# Game.Buildings.RoadConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoadConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_ModificationQuery;
    private Unity.Entities.EntityQuery m_UpdatedNetQuery;
    private Unity.Entities.EntityQuery m_TrafficConfigQuery;
    private Unity.Entities.EntityQuery m_BuildingConfigQuery;
    private Unity.Entities.EntityQuery m_ConnectionQuery;
    private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle;

    public RoadConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void CheckDistance(Game.Net.EdgeGeometry edgeGeometry, Game.Net.EdgeNodeGeometry startGeometry, Game.Net.EdgeNodeGeometry endGeometry, Unity.Mathematics.float3 position, System.Boolean canBeOnRoad, System.Single& maxDistance);
    private static System.Void CheckDistance(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Unity.Mathematics.float3 position, System.Single& maxDistance);
    private static System.Void CheckDistance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& maxDistance);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_ModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModificationQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedNetQuery;
```

- `private Unity.Entities.EntityQuery m_TrafficConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficConfigQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingConfigQuery;
```

- `private Unity.Entities.EntityQuery m_ConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConnectionQuery;
```

- `private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoadConnectionSystem()`  

```csharp
[Preserve]
	public RoadConnectionSystem()
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

- `private static CheckDistance(Game.Net.EdgeGeometry edgeGeometry, Game.Net.EdgeNodeGeometry startGeometry, Game.Net.EdgeNodeGeometry endGeometry, Unity.Mathematics.float3 position, System.Boolean canBeOnRoad, System.Single& maxDistance) : System.Void`  

```csharp
private static void CheckDistance(Bezier4x3 curve, float3 position, ref float maxDistance)
	{
		if (MathUtils.DistanceSquared(MathUtils.Bounds(curve.xz), position.xz) < maxDistance * maxDistance)
		{
			float t;
			float x = MathUtils.Distance(curve.xz, position.xz, out t);
			maxDistance = math.min(x, maxDistance);
		}
	}
```

- `private static CheckDistance(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Unity.Mathematics.float3 position, System.Single& maxDistance) : System.Void`  

```csharp
private static void CheckDistance(Bezier4x3 curve, float3 position, ref float maxDistance)
	{
		if (MathUtils.DistanceSquared(MathUtils.Bounds(curve.xz), position.xz) < maxDistance * maxDistance)
		{
			float t;
			float x = MathUtils.Distance(curve.xz, position.xz, out t);
			maxDistance = math.min(x, maxDistance);
		}
	}
```

- `private static CheckDistance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& maxDistance) : System.Void`  

```csharp
private static void CheckDistance(Bezier4x3 curve, float3 position, ref float maxDistance)
	{
		if (MathUtils.DistanceSquared(MathUtils.Bounds(curve.xz), position.xz) < maxDistance * maxDistance)
		{
			float t;
			float x = MathUtils.Distance(curve.xz, position.xz, out t);
			maxDistance = math.min(x, maxDistance);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_ModificationQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Building>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.SpawnLocation>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Net.Edge>(),
				ComponentType.ReadOnly<ConnectedBuilding>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedNetQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Edge>(), ComponentType.ReadOnly<ConnectedBuilding>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_TrafficConfigQuery = GetEntityQuery(ComponentType.ReadOnly<TrafficConfigurationData>());
		m_BuildingConfigQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		m_ConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<ConnectionLaneData>(), ComponentType.ReadOnly<PrefabData>());
		m_RoadConnectionEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<RoadConnectionUpdated>());
		m_AppliedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		RequireForUpdate(m_ModificationQuery);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeQueue<Entity> replaceRoadConnectionQueue = new NativeQueue<Entity>(Allocator.TempJob);
		NativeList<ReplaceRoad> nativeList = new NativeList<ReplaceRoad>(Allocator.TempJob);
		JobHandle dependencies;
		CheckRoadConnectionJob jobData = new CheckRoadConnectionJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StartNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EndNodeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SpawnLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedBuildingType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_ConnectedBuilding_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ReplaceRoadConnectionQueue = replaceRoadConnectionQueue.AsParallelWriter()
		};
		FillReplacementListJob jobData2 = new FillReplacementListJob
		{
			m_ReplaceRoadConnectionQueue = replaceRoadConnectionQueue,
			m_ReplaceRoadConnection = nativeList
		};
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> updatedNetChunks = m_UpdatedNetQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle dependencies2;
		FindRoadConnectionJob jobData3 = new FindRoadConnectionJob
		{
			m_ConnectedBuildings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_ConnectedBuilding_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BackSideData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_BackSide_RW_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedNetChunks = updatedNetChunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_ReplaceRoadConnection = nativeList.AsDeferredJobArray()
		};
		JobHandle deps;
		ReplaceRoadConnectionJob jobData4 = new ReplaceRoadConnectionJob
		{
			m_CreatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Created_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedBuildings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_ConnectedBuilding_RW_BufferLookup, ref base.CheckedStateRef),
			m_RoadConnectionEventArchetype = m_RoadConnectionEventArchetype,
			m_ReplaceRoadConnection = nativeList,
			m_TrafficConfigurationData = m_TrafficConfigQuery.GetSingleton<TrafficConfigurationData>(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_SourceUpdateData = m_AudioManager.GetSourceUpdateData(out deps)
		};
		JobHandle outJobHandle2;
		NativeList<Entity> connectionPrefabs = m_ConnectionQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle2);
		UpdateSecondaryLanesJob jobData5 = new UpdateSecondaryLanesJob
		{
			m_WaterConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityConsumerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UtilityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UtilityObject_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Secondary_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetLaneArchetypeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneArchetypeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_SpawnLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectionPrefabs = connectionPrefabs,
			m_ReplaceRoadConnection = nativeList,
			m_AppliedTypes = m_AppliedTypes,
			m_BuildingConfigurationData = m_BuildingConfigQuery.GetSingleton<BuildingConfigurationData>(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_ModificationQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
		JobHandle jobHandle3 = jobData3.Schedule(nativeList, 1, JobUtils.CombineDependencies(jobHandle2, dependencies2, outJobHandle, outJobHandle2));
		JobHandle jobHandle4 = IJobExtensions.Schedule(jobData4, JobHandle.CombineDependencies(jobHandle3, deps));
		JobHandle jobHandle5 = jobData5.Schedule(nativeList, 1, jobHandle3);
		replaceRoadConnectionQueue.Dispose(jobHandle2);
		updatedNetChunks.Dispose(jobHandle3);
		connectionPrefabs.Dispose(jobHandle5);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle3);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle4);
		base.Dependency = JobHandle.CombineDependencies(jobHandle4, jobHandle5);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		nativeList.Dispose(base.Dependency);
	}
```


## Nested types

- `Game.Buildings.RoadConnectionSystem+CheckRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+FillReplacementListJob`  
- `Game.Buildings.RoadConnectionSystem+ReplaceRoad`  
- `Game.Buildings.RoadConnectionSystem+FindRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+ReplaceRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+ConnectionLaneKey`  
- `Game.Buildings.RoadConnectionSystem+SpawnLocationData`  
- `Game.Buildings.RoadConnectionSystem+UpdateSecondaryLanesJob`  
- `Game.Buildings.RoadConnectionSystem+TypeHandle`  

