# Game.Simulation.SpawnableAmbienceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SpawnableAmbienceSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Unity.Entities.EntityQuery m_SpawnableQuery;
    private Unity.Entities.EntityQuery m_EmitterQuery;
    private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public SpawnableAmbienceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Unity.Entities.EntityQuery m_SpawnableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableQuery;
```

- `private Unity.Entities.EntityQuery m_EmitterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmitterQuery;
```

- `private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SpawnableAmbienceSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public SpawnableAmbienceSystem()`  

```csharp
[Preserve]
	public SpawnableAmbienceSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ZoneAmbienceSystem = base.World.GetOrCreateSystemManaged<ZoneAmbienceSystem>();
		m_SpawnableQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<BuildingCondition>(),
				ComponentType.ReadOnly<UpdateFrame>(),
				ComponentType.ReadOnly<Renter>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<ResidentialProperty>(),
				ComponentType.ReadOnly<Efficiency>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Abandoned>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Tree>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_EmitterQuery = GetEntityQuery(ComponentType.ReadOnly<AmbienceEmitter>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		Assert.IsTrue(condition: true);
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
		m_SpawnableQuery.ResetFilter();
		m_SpawnableQuery.SetSharedComponentFilter(new UpdateFrame(updateFrame));
		NativeParallelQueue<GroupAmbienceEffect> nativeParallelQueue = new NativeParallelQueue<GroupAmbienceEffect>(math.max(1, JobsUtility.JobWorkerCount / 2), Allocator.TempJob);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new SpawnableAmbienceJob
		{
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableAmbienceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GroupAmbienceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Queue = nativeParallelQueue.AsWriter()
		}, m_SpawnableQuery, base.Dependency);
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new EmitterAmbienceJob
		{
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AmbienceEmitterDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AmbienceEmitterData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Queue = nativeParallelQueue.AsWriter()
		}, m_EmitterQuery, jobHandle);
		JobHandle dependencies;
		JobHandle jobHandle3 = IJobParallelForExtensions.Schedule(new ApplyAmbienceJob
		{
			m_SpawnableQueue = nativeParallelQueue.AsReader(),
			m_ZoneAmbienceMap = m_ZoneAmbienceSystem.GetMap(readOnly: false, out dependencies)
		}, nativeParallelQueue.HashRange, 1, JobHandle.CombineDependencies(jobHandle, dependencies, jobHandle2));
		m_ZoneAmbienceSystem.AddWriter(jobHandle3);
		nativeParallelQueue.Dispose(jobHandle3);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.SpawnableAmbienceSystem+GroupAmbienceEffect`  
- `Game.Simulation.SpawnableAmbienceSystem+ApplyAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+EmitterAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+SpawnableAmbienceJob`  
- `Game.Simulation.SpawnableAmbienceSystem+TypeHandle`  

