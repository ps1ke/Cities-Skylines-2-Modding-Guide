# Game.Simulation.ObjectPolluteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectPolluteSystem : Game.GameSystemBase
{
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private Unity.Entities.EntityQuery m_PollutableObjectQuery;
    private Game.Simulation.ObjectPolluteSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public ObjectPolluteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PollutableObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutableObjectQuery;
```

- `private Game.Simulation.ObjectPolluteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ObjectPolluteSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public ObjectPolluteSystem()`  

```csharp
[Preserve]
	public ObjectPolluteSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		m_PollutableObjectQuery = GetEntityQuery(ComponentType.ReadOnly<Plant>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		m_PollutableObjectQuery.ResetFilter();
		m_PollutableObjectQuery.SetSharedComponentFilter(new UpdateFrame(updateFrame));
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new ObjectPolluteJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PlantType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Plant_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GroundPollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2),
			m_PollutionParameters = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>()
		}, m_PollutableObjectQuery, JobHandle.CombineDependencies(dependencies2, base.Dependency, dependencies));
		m_GroundPollutionSystem.AddReader(jobHandle);
		m_AirPollutionSystem.AddReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.ObjectPolluteSystem+ObjectPolluteJob`  
- `Game.Simulation.ObjectPolluteSystem+TypeHandle`  

