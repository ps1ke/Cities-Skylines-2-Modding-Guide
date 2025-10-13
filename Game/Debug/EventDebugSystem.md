# Game.Debug.EventDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_EventQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Debug.EventDebugSystem+TypeHandle __TypeHandle;

    public EventDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Debug.EventDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.EventDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventDebugSystem()`  

```csharp
[Preserve]
	public EventDebugSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EventQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[7]
			{
				ComponentType.ReadOnly<WeatherPhenomenon>(),
				ComponentType.ReadOnly<OnFire>(),
				ComponentType.ReadOnly<AccidentSite>(),
				ComponentType.ReadOnly<InvolvedInAccident>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<FacingWeather>(),
				ComponentType.ReadOnly<SpectatorSite>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_EventQuery);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new EventGizmoJob
		{
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_EventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Event_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DurationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Duration_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WeatherPhenomenonType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_WeatherPhenomenon_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentTypeHandle, ref base.CheckedStateRef)
		}, m_EventQuery, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.EventDebugSystem+EventGizmoJob`  
- `Game.Debug.EventDebugSystem+TypeHandle`  

