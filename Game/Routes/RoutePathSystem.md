# Game.Routes.RoutePathSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoutePathSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_UpdatedSegmentQuery;
    private Unity.Entities.EntityQuery m_DeletedLaneQuery;
    private Unity.Entities.EntityQuery m_AppliedLaneQuery;
    private Unity.Entities.EntityQuery m_SegmentQuery;
    private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet;
    private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle;

    public RoutePathSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void SetupPathfind(Unity.Entities.Entity entity, Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, Game.Routes.RouteLane startLane, Game.Routes.RouteLane endLane, Game.Prefabs.RouteData route, Game.Prefabs.RouteConnectionData routeConnection, System.Boolean highPriority);
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedSegmentQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSegmentQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedLaneQuery;
```

- `private Unity.Entities.EntityQuery m_AppliedLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_AppliedLaneQuery;
```

- `private Unity.Entities.EntityQuery m_SegmentQuery`  

```csharp
private Unity.Entities.EntityQuery m_SegmentQuery;
```

- `private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet`  

```csharp
private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet;
```

- `private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoutePathSystem()`  

```csharp
[Preserve]
	public RoutePathSystem()
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

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_UpdatedSegmentQuery = GetEntityQuery(ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<Segment>(), ComponentType.ReadWrite<PathTargets>());
		m_DeletedLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Lane>(), ComponentType.Exclude<Temp>());
		m_AppliedLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Applied>(), ComponentType.ReadOnly<Lane>());
		m_SegmentQuery = GetEntityQuery(ComponentType.ReadOnly<Segment>(), ComponentType.ReadOnly<PathElement>(), ComponentType.Exclude<Deleted>());
		m_LazyUpdateSet = new NativeParallelHashSet<Entity>(20, Allocator.Persistent);
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
		m_LazyUpdateSet.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = !m_DeletedLaneQuery.IsEmptyIgnoreFilter && !m_SegmentQuery.IsEmptyIgnoreFilter;
		bool flag2 = !m_AppliedLaneQuery.IsEmptyIgnoreFilter && !m_SegmentQuery.IsEmptyIgnoreFilter;
		bool flag3 = !m_UpdatedSegmentQuery.IsEmptyIgnoreFilter;
		if (!flag && !flag2 && !flag3 && m_LazyUpdateSet.IsEmpty)
		{
			return;
		}
		NativeQueue<Entity> nativeQueue = default(NativeQueue<Entity>);
		NativeQueue<Entity> nativeQueue2 = default(NativeQueue<Entity>);
		NativeParallelHashSet<Entity> nativeParallelHashSet = default(NativeParallelHashSet<Entity>);
		JobHandle jobHandle = default(JobHandle);
		JobHandle jobHandle2 = default(JobHandle);
		if (flag)
		{
			nativeQueue = new NativeQueue<Entity>(Allocator.TempJob);
			jobHandle = JobChunkExtensions.ScheduleParallel(new CheckRoutePathsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdateQueue = nativeQueue.AsParallelWriter()
			}, m_SegmentQuery, base.Dependency);
			JobHandle.ScheduleBatchedJobs();
		}
		if (flag2)
		{
			NativeParallelHashSet<RoutePathType> pathTypeSet = new NativeParallelHashSet<RoutePathType>(10, Allocator.TempJob);
			nativeQueue2 = new NativeQueue<Entity>(Allocator.TempJob);
			CheckAppliedLanesJob jobData = new CheckAppliedLanesJob
			{
				m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathTypeSet = pathTypeSet
			};
			JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(new CheckSegmentRoutes
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathTypeSet = pathTypeSet,
				m_UpdateQueue = nativeQueue2.AsParallelWriter()
			}, dependsOn: JobChunkExtensions.Schedule(jobData, m_AppliedLaneQuery, base.Dependency), query: m_SegmentQuery);
			pathTypeSet.Dispose(jobHandle3);
			jobHandle2 = jobHandle3;
			JobHandle.ScheduleBatchedJobs();
		}
		if (flag || flag3)
		{
			nativeParallelHashSet = new NativeParallelHashSet<Entity>(10, Allocator.Temp);
		}
		if (flag3)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_UpdatedSegmentQuery.ToArchetypeChunkArray(Allocator.TempJob);
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Segment> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Owner> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PathTargets> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_PathTargets_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Temp> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferLookup<RouteWaypoint> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteLane> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Position> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteData> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteConnectionData> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef);
			base.Dependency.Complete();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<Segment> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<Owner> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
				NativeArray<PathTargets> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle3);
				NativeArray<PrefabRef> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle5);
				bool highPriority = archetypeChunk.Has(ref typeHandle4);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					Entity entity = nativeArray2[j];
					Segment segment = nativeArray3[j];
					Owner owner = nativeArray4[j];
					PathTargets value = nativeArray5[j];
					PrefabRef prefabRef = nativeArray6[j];
					if (!bufferLookup.HasBuffer(owner.m_Owner))
					{
						continue;
					}
					DynamicBuffer<RouteWaypoint> dynamicBuffer = bufferLookup[owner.m_Owner];
					int num = segment.m_Index + 1;
					if (num == dynamicBuffer.Length)
					{
						num = 0;
					}
					Entity waypoint = dynamicBuffer[segment.m_Index].m_Waypoint;
					Entity waypoint2 = dynamicBuffer[num].m_Waypoint;
					if (componentLookup.HasComponent(waypoint) && componentLookup.HasComponent(waypoint2))
					{
						RouteLane startLane = componentLookup[waypoint];
						RouteLane endLane = componentLookup[waypoint2];
						float2 @float = new float2(startLane.m_EndCurvePos, endLane.m_StartCurvePos);
						if (!(value.m_StartLane == startLane.m_EndLane) || !(value.m_EndLane == endLane.m_StartLane) || !math.all(math.abs(value.m_CurvePositions - @float) < 0.001f))
						{
							value.m_StartLane = startLane.m_EndLane;
							value.m_EndLane = endLane.m_StartLane;
							value.m_CurvePositions = @float;
							float3 position = componentLookup2[waypoint].m_Position;
							float3 position2 = componentLookup2[waypoint2].m_Position;
							RouteData route = componentLookup3[prefabRef.m_Prefab];
							RouteConnectionData routeConnection = componentLookup4[prefabRef.m_Prefab];
							SetupPathfind(entity, position, position2, startLane, endLane, route, routeConnection, highPriority);
							nativeParallelHashSet.Add(entity);
							m_LazyUpdateSet.Remove(entity);
							nativeArray5[j] = value;
						}
					}
				}
			}
			nativeArray.Dispose();
		}
		if (flag)
		{
			BufferLookup<RouteWaypoint> bufferLookup2 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteLane> componentLookup5 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Position> componentLookup6 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Segment> componentLookup7 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Owner> componentLookup8 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<PrefabRef> componentLookup9 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteData> componentLookup10 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteConnectionData> componentLookup11 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef);
			jobHandle.Complete();
			base.Dependency.Complete();
			Entity item;
			while (nativeQueue.TryDequeue(out item))
			{
				if (nativeParallelHashSet.Add(item))
				{
					m_LazyUpdateSet.Remove(item);
					Segment segment2 = componentLookup7[item];
					Owner owner2 = componentLookup8[item];
					PrefabRef prefabRef2 = componentLookup9[item];
					DynamicBuffer<RouteWaypoint> dynamicBuffer2 = bufferLookup2[owner2.m_Owner];
					int num2 = segment2.m_Index + 1;
					if (num2 == dynamicBuffer2.Length)
					{
						num2 = 0;
					}
					Entity waypoint3 = dynamicBuffer2[segment2.m_Index].m_Waypoint;
					Entity waypoint4 = dynamicBuffer2[num2].m_Waypoint;
					RouteLane startLane2 = componentLookup5[waypoint3];
					RouteLane endLane2 = componentLookup5[waypoint4];
					float3 position3 = componentLookup6[waypoint3].m_Position;
					float3 position4 = componentLookup6[waypoint4].m_Position;
					RouteData route2 = componentLookup10[prefabRef2.m_Prefab];
					RouteConnectionData routeConnection2 = componentLookup11[prefabRef2.m_Prefab];
					SetupPathfind(item, position3, position4, startLane2, endLane2, route2, routeConnection2, highPriority: false);
				}
			}
		}
		if (flag2)
		{
			jobHandle2.Complete();
			Entity item2;
			while (nativeQueue2.TryDequeue(out item2))
			{
				if (!nativeParallelHashSet.IsCreated || !nativeParallelHashSet.Contains(item2))
				{
					m_LazyUpdateSet.Add(item2);
				}
			}
		}
		if (!m_LazyUpdateSet.IsEmpty && (!nativeParallelHashSet.IsCreated || nativeParallelHashSet.IsEmpty))
		{
			BufferLookup<RouteWaypoint> bufferLookup3 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteLane> componentLookup12 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Position> componentLookup13 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Segment> componentLookup14 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Owner> componentLookup15 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Deleted> componentLookup16 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<PrefabRef> componentLookup17 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteData> componentLookup18 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteData_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<RouteConnectionData> componentLookup19 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef);
			base.Dependency.Complete();
			NativeParallelHashSet<Entity>.Enumerator enumerator = m_LazyUpdateSet.GetEnumerator();
			while (enumerator.MoveNext())
			{
				Entity current = enumerator.Current;
				m_LazyUpdateSet.Remove(current);
				enumerator.Dispose();
				enumerator = m_LazyUpdateSet.GetEnumerator();
				if (componentLookup14.HasComponent(current) && !componentLookup16.HasComponent(current))
				{
					Segment segment3 = componentLookup14[current];
					Owner owner3 = componentLookup15[current];
					PrefabRef prefabRef3 = componentLookup17[current];
					DynamicBuffer<RouteWaypoint> dynamicBuffer3 = bufferLookup3[owner3.m_Owner];
					int num3 = segment3.m_Index + 1;
					if (num3 == dynamicBuffer3.Length)
					{
						num3 = 0;
					}
					Entity waypoint5 = dynamicBuffer3[segment3.m_Index].m_Waypoint;
					Entity waypoint6 = dynamicBuffer3[num3].m_Waypoint;
					RouteLane startLane3 = componentLookup12[waypoint5];
					RouteLane endLane3 = componentLookup12[waypoint6];
					float3 position5 = componentLookup13[waypoint5].m_Position;
					float3 position6 = componentLookup13[waypoint6].m_Position;
					RouteData route3 = componentLookup18[prefabRef3.m_Prefab];
					RouteConnectionData routeConnection3 = componentLookup19[prefabRef3.m_Prefab];
					SetupPathfind(current, position5, position6, startLane3, endLane3, route3, routeConnection3, highPriority: false);
					break;
				}
			}
			enumerator.Dispose();
		}
		if (nativeQueue.IsCreated)
		{
			nativeQueue.Dispose();
		}
		if (nativeQueue2.IsCreated)
		{
			nativeQueue2.Dispose();
		}
		if (nativeParallelHashSet.IsCreated)
		{
			nativeParallelHashSet.Dispose();
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LazyUpdateSet.Clear();
	}
```

- `private SetupPathfind(Unity.Entities.Entity entity, Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, Game.Routes.RouteLane startLane, Game.Routes.RouteLane endLane, Game.Prefabs.RouteData route, Game.Prefabs.RouteConnectionData routeConnection, System.Boolean highPriority) : System.Void`  

```csharp
private void SetupPathfind(Entity entity, float3 startPos, float3 endPos, RouteLane startLane, RouteLane endLane, RouteData route, RouteConnectionData routeConnection, bool highPriority)
	{
		PathfindParameters parameters = new PathfindParameters
		{
			m_MaxSpeed = 277.77777f,
			m_WalkSpeed = 5.555556f,
			m_Weights = new PathfindWeights(1f, 1f, 1f, 1f),
			m_PathfindFlags = (PathfindFlags.Stable | PathfindFlags.IgnoreFlow),
			m_IgnoredRules = (RuleFlags.HasBlockage | RuleFlags.ForbidCombustionEngines | RuleFlags.ForbidHeavyTraffic | RuleFlags.ForbidPrivateTraffic | RuleFlags.ForbidSlowTraffic),
			m_Methods = RouteUtils.GetPathMethods(routeConnection.m_RouteConnectionType, route.m_Type, routeConnection.m_RouteTrackType, routeConnection.m_RouteRoadType, routeConnection.m_RouteSizeClass)
		};
		if (routeConnection.m_RouteConnectionType != RouteConnectionType.Road || routeConnection.m_RouteRoadType != RoadTypes.Car)
		{
			parameters.m_IgnoredRules |= RuleFlags.ForbidTransitTraffic;
		}
		PathfindAction action = new PathfindAction(1, 1, Allocator.Persistent, parameters, SetupTargetType.None, SetupTargetType.None);
		action.data.m_StartTargets[0] = new PathTarget(startLane.m_EndLane, startLane.m_EndLane, startLane.m_EndCurvePos, 0f);
		action.data.m_EndTargets[0] = new PathTarget(endLane.m_StartLane, endLane.m_StartLane, endLane.m_StartCurvePos, 0f);
		PathEventData eventData = new PathEventData
		{
			m_Position1 = startPos,
			m_Position2 = endPos
		};
		m_PathfindQueueSystem.Enqueue(action, entity, default(JobHandle), uint.MaxValue, this, eventData, highPriority);
	}
```


## Nested types

- `Game.Routes.RoutePathSystem+RoutePathType`  
- `Game.Routes.RoutePathSystem+CheckRoutePathsJob`  
- `Game.Routes.RoutePathSystem+CheckAppliedLanesJob`  
- `Game.Routes.RoutePathSystem+CheckSegmentRoutes`  
- `Game.Routes.RoutePathSystem+TypeHandle`  

