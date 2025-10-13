# Game.Buildings.CityServiceEfficiencySystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityServiceEfficiencySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdatedBudgetQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_ChangedBuildingQuery;
    private Game.Buildings.CityServiceEfficiencySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_339138653_0;
    private Unity.Entities.EntityQuery __query_339138653_1;

    public CityServiceEfficiencySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdatedBudgetQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBudgetQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ChangedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChangedBuildingQuery;
```

- `private Game.Buildings.CityServiceEfficiencySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.CityServiceEfficiencySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_339138653_0`  

```csharp
private Unity.Entities.EntityQuery __query_339138653_0;
```

- `private Unity.Entities.EntityQuery __query_339138653_1`  

```csharp
private Unity.Entities.EntityQuery __query_339138653_1;
```


## Constructors

- `public CityServiceEfficiencySystem()`  

```csharp
[Preserve]
	public CityServiceEfficiencySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_339138653_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAllRW<ServiceBudgetData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_339138653_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UpdatedBudgetQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceBudgetData>(), ComponentType.ReadOnly<Updated>());
		m_ChangedBuildingQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<CityServiceUpkeep>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadWrite<Efficiency>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadWrite<Efficiency>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireAnyForUpdate(m_UpdatedBudgetQuery, m_ChangedBuildingQuery);
		RequireForUpdate<ServiceBudgetData>();
		RequireForUpdate<BuildingEfficiencyParameterData>();
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
		BuildingEfficiencyParameterData singleton = __query_339138653_0.GetSingleton<BuildingEfficiencyParameterData>();
		BuildingStateEfficiencyJob jobData = new BuildingStateEfficiencyJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceObjectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpkeepDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceBudgets = __query_339138653_1.GetSingletonBuffer<ServiceBudgetData>(isReadOnly: true),
			m_ServiceBudgetEfficiencyFactor = singleton.m_ServiceBudgetEfficiencyFactor
		};
		EntityQuery query = ((!m_UpdatedBudgetQuery.IsEmptyIgnoreFilter) ? m_BuildingQuery : m_ChangedBuildingQuery);
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, query, base.Dependency);
	}
```


## Nested types

- `Game.Buildings.CityServiceEfficiencySystem+BuildingStateEfficiencyJob`  
- `Game.Buildings.CityServiceEfficiencySystem+TypeHandle`  

