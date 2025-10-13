# Game.Simulation.CountCompanyDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountCompanyDataSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_FreeIndustrialQuery;
    private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
    private Unity.Entities.EntityQuery m_StorageCompanyQuery;
    private Unity.Entities.EntityQuery m_ProcessDataQuery;
    private Unity.Entities.EntityQuery m_CityServiceQuery;
    private Unity.Entities.EntityQuery m_SpawnableQuery;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers;
    private Unity.Collections.NativeArray<System.Int32> m_Production;
    private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities;
    private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables;
    private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables;
    private Unity.Collections.NativeArray<System.Int32> m_Demand;
    private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies;
    private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies;
    private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless;
    private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle;

    public CountCompanyDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas GetCommercialCompanyDatas(Unity.Jobs.JobHandle& deps);
    public Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas GetIndustrialCompanyDatas(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetProduction(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.CountCompanyDataSystem+CompanyDataItem> m_DataQueue;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_FreeIndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeIndustrialQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_StorageCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageCompanyQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessDataQuery;
```

- `private Unity.Entities.EntityQuery m_CityServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityServiceQuery;
```

- `private Unity.Entities.EntityQuery m_SpawnableQuery`  

```csharp
private Unity.Entities.EntityQuery m_SpawnableQuery;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CurrentProductionWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MaxProductionWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CurrentServiceWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MaxServiceWorkers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Production`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Production;
```

- `private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_SalesCapacities;
```

- `private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_CurrentAvailables;
```

- `private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_TotalAvailables;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Demand`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Demand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ProductionCompanies;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ServiceCompanies;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ProductionPropertyless;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ServicePropertyless;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountCompanyDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CountCompanyDataSystem()`  

```csharp
[Preserve]
	public CountCompanyDataSystem()
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

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public void AddReader(JobHandle reader)
	{
		m_ReadDependencies = JobHandle.CombineDependencies(m_ReadDependencies, reader);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetCommercialCompanyDatas(Unity.Jobs.JobHandle& deps) : Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas`  

```csharp
public CommercialCompanyDatas GetCommercialCompanyDatas(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return new CommercialCompanyDatas
		{
			m_CurrentAvailables = m_CurrentAvailables,
			m_ProduceCapacity = m_SalesCapacities,
			m_ServiceCompanies = m_ServiceCompanies,
			m_ServicePropertyless = m_ServicePropertyless,
			m_TotalAvailables = m_TotalAvailables,
			m_CurrentServiceWorkers = m_CurrentServiceWorkers,
			m_MaxServiceWorkers = m_MaxServiceWorkers
		};
	}
```

- `public GetIndustrialCompanyDatas(Unity.Jobs.JobHandle& deps) : Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas`  

```csharp
public IndustrialCompanyDatas GetIndustrialCompanyDatas(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return new IndustrialCompanyDatas
		{
			m_Demand = m_Demand,
			m_Production = m_Production,
			m_ProductionCompanies = m_ProductionCompanies,
			m_ProductionPropertyless = m_ProductionPropertyless,
			m_CurrentProductionWorkers = m_CurrentProductionWorkers,
			m_MaxProductionWorkers = m_MaxProductionWorkers
		};
	}
```

- `public GetProduction(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetProduction(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_Production;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 1;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_CompanyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<WorkProvider>(), ComponentType.ReadOnly<Resources>(), ComponentType.Exclude<Game.Companies.StorageCompany>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ProcessDataQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.Exclude<ServiceCompanyData>());
		int resourceCount = EconomyUtils.ResourceCount;
		m_CurrentProductionWorkers = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_MaxProductionWorkers = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_CurrentServiceWorkers = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_MaxServiceWorkers = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_Production = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_SalesCapacities = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_CurrentAvailables = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_TotalAvailables = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_Demand = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ProductionCompanies = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ServiceCompanies = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ProductionPropertyless = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ServicePropertyless = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_DataQueue = new NativeQueue<CompanyDataItem>(Allocator.Persistent);
		RequireForUpdate(m_CompanyQuery);
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_DemandParameterQuery);
		RequireForUpdate(m_ProcessDataQuery);
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
		m_CurrentProductionWorkers.Dispose();
		m_MaxProductionWorkers.Dispose();
		m_CurrentServiceWorkers.Dispose();
		m_MaxServiceWorkers.Dispose();
		m_Production.Dispose();
		m_SalesCapacities.Dispose();
		m_CurrentAvailables.Dispose();
		m_TotalAvailables.Dispose();
		m_Demand.Dispose();
		m_ProductionCompanies.Dispose();
		m_ServiceCompanies.Dispose();
		m_ProductionPropertyless.Dispose();
		m_ServicePropertyless.Dispose();
		m_DataQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Production.Fill(0);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(new CountCompanyDataJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceAvailableType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencyBuf = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_DataQueue = m_DataQueue.AsParallelWriter()
		}, m_CompanyQuery, JobHandle.CombineDependencies(base.Dependency, m_WriteDependencies, m_ReadDependencies));
		SumJob jobData = new SumJob
		{
			m_Demand = m_Demand,
			m_Production = m_Production,
			m_CurrentAvailables = m_CurrentAvailables,
			m_ProductionCompanies = m_ProductionCompanies,
			m_ProductionPropertyless = m_ProductionPropertyless,
			m_SalesCapacities = m_SalesCapacities,
			m_ServiceCompanies = m_ServiceCompanies,
			m_ServicePropertyless = m_ServicePropertyless,
			m_TotalAvailables = m_TotalAvailables,
			m_CurrentProductionWorkers = m_CurrentProductionWorkers,
			m_CurrentServiceWorkers = m_CurrentServiceWorkers,
			m_MaxProductionWorkers = m_MaxProductionWorkers,
			m_MaxServiceWorkers = m_MaxServiceWorkers,
			m_DataQueue = m_DataQueue
		};
		base.Dependency = IJobExtensions.Schedule(jobData, dependsOn);
		m_WriteDependencies = base.Dependency;
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
		m_CurrentProductionWorkers.Fill(0);
		m_MaxProductionWorkers.Fill(0);
		m_CurrentServiceWorkers.Fill(0);
		m_MaxServiceWorkers.Fill(0);
		m_Production.Fill(0);
		m_SalesCapacities.Fill(0);
		m_CurrentAvailables.Fill(0);
		m_TotalAvailables.Fill(0);
		m_Demand.Fill(0);
		m_ProductionCompanies.Fill(0);
		m_ServiceCompanies.Fill(0);
		m_ProductionPropertyless.Fill(0);
		m_ServicePropertyless.Fill(0);
	}
```


## Nested types

- `Game.Simulation.CountCompanyDataSystem+CommercialCompanyDatas`  
- `Game.Simulation.CountCompanyDataSystem+IndustrialCompanyDatas`  
- `Game.Simulation.CountCompanyDataSystem+CompanyDataItem`  
- `Game.Simulation.CountCompanyDataSystem+SumJob`  
- `Game.Simulation.CountCompanyDataSystem+CountCompanyDataJob`  
- `Game.Simulation.CountCompanyDataSystem+TypeHandle`  

