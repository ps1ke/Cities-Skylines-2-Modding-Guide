# Game.Net.ConnectionWarningSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ConnectionWarningSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_NewGameQuery;
    private Unity.Entities.EntityQuery m_WaterConfigQuery;
    private Unity.Entities.EntityQuery m_ElectricityConfigQuery;
    private Unity.Entities.EntityQuery m_TrafficConfigQuery;
    private System.Boolean m_IsNewGame;
    private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle;

    public ConnectionWarningSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private T GetConfigData<T>(Unity.Entities.EntityQuery query);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_NewGameQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewGameQuery;
```

- `private Unity.Entities.EntityQuery m_WaterConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterConfigQuery;
```

- `private Unity.Entities.EntityQuery m_ElectricityConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ElectricityConfigQuery;
```

- `private Unity.Entities.EntityQuery m_TrafficConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficConfigQuery;
```

- `private System.Boolean m_IsNewGame`  

```csharp
private System.Boolean m_IsNewGame;
```

- `private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.ConnectionWarningSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ConnectionWarningSystem()`  

```csharp
[Preserve]
	public ConnectionWarningSystem()
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

- `private GetConfigData<T>(Unity.Entities.EntityQuery query) : T`  

```csharp
private T GetConfigData<T>(Unity.Entities.EntityQuery query);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_AreaUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Areas.UpdateCollectSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_UpdateQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>(),
				ComponentType.ReadOnly<Game.Routes.TakeoffLocation>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<RoadConnectionUpdated>(),
				ComponentType.ReadOnly<Game.Common.Event>()
			}
		});
		m_NewGameQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>(),
				ComponentType.ReadOnly<Game.Routes.TakeoffLocation>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_WaterConfigQuery = GetEntityQuery(ComponentType.ReadOnly<WaterPipeParameterData>());
		m_ElectricityConfigQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityParameterData>());
		m_TrafficConfigQuery = GetEntityQuery(ComponentType.ReadOnly<TrafficConfigurationData>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_IsNewGame = serializationContext.purpose == Purpose.NewGame;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery entityQuery = (m_IsNewGame ? m_NewGameQuery : m_UpdateQuery);
		m_IsNewGame = false;
		bool flag = !entityQuery.IsEmptyIgnoreFilter;
		bool mapTilesUpdated = m_AreaUpdateCollectSystem.mapTilesUpdated;
		if (flag || mapTilesUpdated)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(32, Allocator.TempJob);
			JobHandle job = base.Dependency;
			if (flag)
			{
				JobHandle outJobHandle;
				NativeList<ArchetypeChunk> chunks = entityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
				JobHandle jobHandle = IJobExtensions.Schedule(new CollectOwnersJob
				{
					m_Chunks = chunks,
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_RoadConnectionUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RoadConnectionUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Owners = nativeList
				}, JobHandle.CombineDependencies(job, outJobHandle));
				chunks.Dispose(jobHandle);
				job = jobHandle;
			}
			if (mapTilesUpdated)
			{
				JobHandle dependencies;
				JobHandle dependencies2;
				JobHandle dependencies3;
				JobHandle jobHandle2 = IJobExtensions.Schedule(new CollectOwnersJob2
				{
					m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
					m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
					m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
					m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
					m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
					m_Bounds = m_AreaUpdateCollectSystem.GetUpdatedMapTileBounds(out dependencies3),
					m_Owners = nativeList
				}, JobUtils.CombineDependencies(job, dependencies, dependencies2, dependencies3));
				m_NetSearchSystem.AddNetSearchTreeReader(jobHandle2);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle2);
				m_AreaUpdateCollectSystem.AddMapTileBoundsReader(jobHandle2);
				job = jobHandle2;
			}
			JobHandle dependencies4;
			JobHandle jobHandle3 = new CheckOwnersJob
			{
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_Owners = nativeList.AsDeferredJobArray(),
				m_WaterPipeParameterData = GetConfigData<WaterPipeParameterData>(m_WaterConfigQuery),
				m_ElectricityParameterData = GetConfigData<ElectricityParameterData>(m_ElectricityConfigQuery),
				m_TrafficConfigurationData = GetConfigData<TrafficConfigurationData>(m_TrafficConfigQuery),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies4),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ResourceConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TakeoffLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TakeoffLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AccessLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Transformer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MapTileData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRouteConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabLocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabResourceConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_IconElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Notifications_IconElement_RO_BufferLookup, ref base.CheckedStateRef)
			}.Schedule(nativeList, 1, JobHandle.CombineDependencies(job, dependencies4));
			nativeList.Dispose(jobHandle3);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle3);
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle3);
			base.Dependency = jobHandle3;
		}
	}
```


## Nested types

- `Game.Net.ConnectionWarningSystem+CollectOwnersJob`  
- `Game.Net.ConnectionWarningSystem+CollectOwnersJob2`  
- `Game.Net.ConnectionWarningSystem+PathfindElement`  
- `Game.Net.ConnectionWarningSystem+BufferElement`  
- `Game.Net.ConnectionWarningSystem+Connection`  
- `Game.Net.ConnectionWarningSystem+CheckOwnersJob`  
- `Game.Net.ConnectionWarningSystem+TypeHandle`  

