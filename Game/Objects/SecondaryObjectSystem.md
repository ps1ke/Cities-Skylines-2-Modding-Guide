# Game.Objects.SecondaryObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SecondaryObjectSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.ComponentTypeSet m_AppliedTypes;
    private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes;
    private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
    private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle;

    public SecondaryObjectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateLanes(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue);
    private System.Void UpdateObjects(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AppliedTypes;
```

- `private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes;
```

- `private Unity.Entities.ComponentTypeSet m_TempAnimationTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TempAnimationTypes;
```

- `private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SecondaryObjectSystem()`  

```csharp
[Preserve]
	public SecondaryObjectSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_ObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<SubObject>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Building>() }
		});
		m_LaneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.UtilityLane>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Owner>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_AppliedTypes = new ComponentTypeSet(ComponentType.ReadWrite<Applied>(), ComponentType.ReadWrite<Created>(), ComponentType.ReadWrite<Updated>());
		m_SecondaryOwnerTypes = new ComponentTypeSet(ComponentType.ReadWrite<Secondary>(), ComponentType.ReadWrite<Owner>());
		m_TempAnimationTypes = new ComponentTypeSet(ComponentType.ReadWrite<Temp>(), ComponentType.ReadWrite<Game.Tools.Animation>(), ComponentType.ReadWrite<InterpolatedTransform>());
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
		bool flag = !m_ObjectQuery.IsEmptyIgnoreFilter;
		bool flag2 = !m_LaneQuery.IsEmptyIgnoreFilter;
		if (flag || flag2)
		{
			NativeQueue<UpdateData> updateQueue = new NativeQueue<UpdateData>(Allocator.TempJob);
			if (flag)
			{
				UpdateObjects(updateQueue);
			}
			if (flag2)
			{
				UpdateLanes(updateQueue);
			}
			updateQueue.Dispose(base.Dependency);
		}
	}
```

- `private UpdateLanes(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue) : System.Void`  

```csharp
private void UpdateLanes(NativeQueue<UpdateData> updateQueue)
	{
		NativeParallelMultiHashMap<Entity, UpdateData> updateMap = new NativeParallelMultiHashMap<Entity, UpdateData>(100, Allocator.TempJob);
		FillUpdateMapJob jobData = new FillUpdateMapJob
		{
			m_UpdateQueue = updateQueue,
			m_UpdateMap = updateMap
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new SecondaryLaneAnchorJob
		{
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UtilityLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_UpdateMap = updateMap
		}, dependsOn: IJobExtensions.Schedule(jobData, base.Dependency), query: m_LaneQuery);
		updateMap.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `private UpdateObjects(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue) : System.Void`  

```csharp
private void UpdateObjects(NativeQueue<UpdateData> updateQueue)
	{
		NativeQueue<SubObjectOwnerData> ownerQueue = new NativeQueue<SubObjectOwnerData>(Allocator.TempJob);
		NativeList<SubObjectOwnerData> nativeList = new NativeList<SubObjectOwnerData>(Allocator.TempJob);
		CheckSubObjectOwnersJob jobData = new CheckSubObjectOwnersJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Secondary_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_AppliedTypes = m_AppliedTypes,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_OwnerQueue = ownerQueue.AsParallelWriter()
		};
		CollectSubObjectOwnersJob jobData2 = new CollectSubObjectOwnersJob
		{
			m_OwnerQueue = ownerQueue,
			m_OwnerList = nativeList
		};
		UpdateSubObjectsJob jobData3 = new UpdateSubObjectsJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrafficLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrafficLightData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrafficSignData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrafficSignData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStreetLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StreetLightData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLaneDirectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LaneDirectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabThemeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ThemeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceholderObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Secondary_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_TrafficLight_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StreetLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_StreetLight_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetNodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetEdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneSignalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneSignal_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SecondaryLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficLightsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrafficLights_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetCompositionObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_PlaceholderObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ObjectRequirements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ObjectRequirementElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_DefaultNetLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_DefaultNetLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
			m_RandomSeed = RandomSeed.Next(),
			m_DefaultTheme = m_CityConfigurationSystem.defaultTheme,
			m_AppliedTypes = m_AppliedTypes,
			m_SecondaryOwnerTypes = m_SecondaryOwnerTypes,
			m_TempAnimationTypes = m_TempAnimationTypes,
			m_OwnerList = nativeList.AsDeferredJobArray(),
			m_UpdateQueue = updateQueue.AsParallelWriter(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, m_ObjectQuery, base.Dependency);
		JobHandle jobHandle = IJobExtensions.Schedule(jobData2, dependsOn);
		JobHandle jobHandle2 = jobData3.Schedule(nativeList, 1, jobHandle);
		ownerQueue.Dispose(jobHandle);
		nativeList.Dispose(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Objects.SecondaryObjectSystem+UpdateData`  
- `Game.Objects.SecondaryObjectSystem+SubObjectOwnerData`  
- `Game.Objects.SecondaryObjectSystem+TrafficSignNeeds`  
- `Game.Objects.SecondaryObjectSystem+TrafficSignData`  
- `Game.Objects.SecondaryObjectSystem+StreetLightData`  
- `Game.Objects.SecondaryObjectSystem+UtilityObjectData`  
- `Game.Objects.SecondaryObjectSystem+UtilityNodeData`  
- `Game.Objects.SecondaryObjectSystem+TargetLaneData`  
- `Game.Objects.SecondaryObjectSystem+PlaceholderKey`  
- `Game.Objects.SecondaryObjectSystem+UpdateSecondaryObjectsData`  
- `Game.Objects.SecondaryObjectSystem+FillUpdateMapJob`  
- `Game.Objects.SecondaryObjectSystem+SecondaryLaneAnchorJob`  
- `Game.Objects.SecondaryObjectSystem+CheckSubObjectOwnersJob`  
- `Game.Objects.SecondaryObjectSystem+CollectSubObjectOwnersJob`  
- `Game.Objects.SecondaryObjectSystem+UpdateSubObjectsJob`  
- `Game.Objects.SecondaryObjectSystem+TypeHandle`  

