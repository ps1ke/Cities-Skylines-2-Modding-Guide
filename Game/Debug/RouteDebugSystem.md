# Game.Debug.RouteDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_RouteGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Debug.BaseDebugSystem+Option m_RouteOption;
    private Game.Debug.BaseDebugSystem+Option m_LaneConnectionOption;
    private Game.Debug.RouteDebugSystem+TypeHandle __TypeHandle;

    public RouteDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RouteGroup`  

```csharp
private Unity.Entities.EntityQuery m_RouteGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RouteOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_LaneConnectionOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_LaneConnectionOption;
```

- `private Game.Debug.RouteDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.RouteDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteDebugSystem()`  

```csharp
[Preserve]
	public RouteDebugSystem()
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
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_RouteGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Route>(),
				ComponentType.ReadOnly<RouteWaypoint>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Hidden>()
			}
		}, new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Hidden>()
			}
		});
		m_RouteOption = AddOption("Routes", defaultEnabled: true);
		m_LaneConnectionOption = AddOption("Lane Connections", defaultEnabled: true);
		RequireForUpdate(m_RouteGroup);
		base.Enabled = false;
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

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new RouteGizmoJob
		{
			m_RouteOption = m_RouteOption.enabled,
			m_LaneConnectionOption = m_LaneConnectionOption.enabled,
			m_RouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Route_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Position_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AccessLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaypointType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Error_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, m_RouteGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.RouteDebugSystem+RouteGizmoJob`  
- `Game.Debug.RouteDebugSystem+TypeHandle`  

