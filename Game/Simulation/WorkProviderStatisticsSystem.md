# Game.Simulation.WorkProviderStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkProviderStatisticsSystem : Game.GameSystemBase
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_WorkProviderQuery;
    private Game.Simulation.WorkProviderStatisticsSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1149970541_0;
    private Unity.Entities.EntityQuery __query_1149970541_1;

    public WorkProviderStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_WorkProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkProviderQuery;
```

- `private Game.Simulation.WorkProviderStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WorkProviderStatisticsSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1149970541_0`  

```csharp
private Unity.Entities.EntityQuery __query_1149970541_0;
```

- `private Unity.Entities.EntityQuery __query_1149970541_1`  

```csharp
private Unity.Entities.EntityQuery __query_1149970541_1;
```


## Constructors

- `public WorkProviderStatisticsSystem()`  

```csharp
[Preserve]
	public WorkProviderStatisticsSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<PoliceConfigurationData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1149970541_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<WorkProviderParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1149970541_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 8192;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_WorkProviderQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<WorkProvider>(),
				ComponentType.ReadOnly<Employee>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_WorkProviderQuery);
		RequireForUpdate<WorkProviderParameterData>();
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
		PoliceConfigurationData singleton = __query_1149970541_0.GetSingleton<PoliceConfigurationData>();
		if (!base.EntityManager.HasEnabledComponent<Locked>(singleton.m_PoliceServicePrefab))
		{
			NativeAccumulator<AverageFloat> freeSeniorWorkplaces = new NativeAccumulator<AverageFloat>(Allocator.TempJob);
			CountSeniorWorkplacesJob jobData = new CountSeniorWorkplacesJob
			{
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WorkProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_FreeWorkplacesType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_FreeWorkplaces_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SeniorEmployeeLevel = __query_1149970541_1.GetSingleton<WorkProviderParameterData>().m_SeniorEmployeeLevel,
				m_FreeSeniorWorkplaces = freeSeniorWorkplaces.AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_WorkProviderQuery, base.Dependency);
			JobHandle deps;
			StatisticsJob jobData2 = new StatisticsJob
			{
				m_FreeSeniorWorkplaces = freeSeniorWorkplaces,
				m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps)
			};
			base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, deps));
			m_CityStatisticsSystem.AddWriter(base.Dependency);
			freeSeniorWorkplaces.Dispose(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.WorkProviderStatisticsSystem+CountSeniorWorkplacesJob`  
- `Game.Simulation.WorkProviderStatisticsSystem+StatisticsJob`  
- `Game.Simulation.WorkProviderStatisticsSystem+TypeHandle`  

