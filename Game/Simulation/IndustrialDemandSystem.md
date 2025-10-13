# Game.Simulation.IndustrialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialDemandSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_IndustrialQuery;
    private Unity.Entities.EntityQuery m_OfficeQuery;
    private Unity.Entities.EntityQuery m_StorageCompanyQuery;
    private Unity.Entities.EntityQuery m_ProcessDataQuery;
    private Unity.Entities.EntityQuery m_CityServiceQuery;
    private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand;
    private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands;
    private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands;
    private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands;
    private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands;
    private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
    private Unity.Collections.NativeArray<System.Int32> m_FreeStorages;
    private Unity.Collections.NativeArray<System.Int32> m_Storages;
    private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Int32 m_LastIndustrialCompanyDemand;
    private System.Int32 m_LastIndustrialBuildingDemand;
    private System.Int32 m_LastStorageCompanyDemand;
    private System.Int32 m_LastStorageBuildingDemand;
    private System.Int32 m_LastOfficeCompanyDemand;
    private System.Int32 m_LastOfficeBuildingDemand;
    private System.Single m_IndustrialOfficeTaxEffectDemandOffset;
    private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kStorageProductionDemand;
    private static readonly System.Int32 kStorageCompanyEstimateLimit;

    public System.Int32 industrialCompanyDemand { get; }
    public System.Int32 industrialBuildingDemand { get; }
    public System.Int32 storageCompanyDemand { get; }
    public System.Int32 storageBuildingDemand { get; }
    public System.Int32 officeCompanyDemand { get; }
    public System.Int32 officeBuildingDemand { get; }

    public IndustrialDemandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetBuildingDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetConsumption(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetIndustrialDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetIndustrialResourceDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetOfficeDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetResourceDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetStorageBuildingDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetStorageCompanyDemands(Unity.Jobs.JobHandle& deps);
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

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialQuery;
```

- `private Unity.Entities.EntityQuery m_OfficeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OfficeQuery;
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

- `private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_IndustrialCompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_IndustrialBuildingDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_StorageCompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_StorageBuildingDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_OfficeCompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_OfficeBuildingDemand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_OfficeDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialCompanyDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialZoningDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IndustrialBuildingDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StorageBuildingDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StorageCompanyDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeProperties`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeStorages`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeStorages;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Storages`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Storages;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StorageCapacities;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Int32 m_LastIndustrialCompanyDemand`  

```csharp
private System.Int32 m_LastIndustrialCompanyDemand;
```

- `private System.Int32 m_LastIndustrialBuildingDemand`  

```csharp
private System.Int32 m_LastIndustrialBuildingDemand;
```

- `private System.Int32 m_LastStorageCompanyDemand`  

```csharp
private System.Int32 m_LastStorageCompanyDemand;
```

- `private System.Int32 m_LastStorageBuildingDemand`  

```csharp
private System.Int32 m_LastStorageBuildingDemand;
```

- `private System.Int32 m_LastOfficeCompanyDemand`  

```csharp
private System.Int32 m_LastOfficeCompanyDemand;
```

- `private System.Int32 m_LastOfficeBuildingDemand`  

```csharp
private System.Int32 m_LastOfficeBuildingDemand;
```

- `private System.Single m_IndustrialOfficeTaxEffectDemandOffset`  

```csharp
private System.Single m_IndustrialOfficeTaxEffectDemandOffset;
```

- `private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialDemandSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kStorageProductionDemand`  

```csharp
private static readonly System.Int32 kStorageProductionDemand;
```

- `private static readonly System.Int32 kStorageCompanyEstimateLimit`  

```csharp
private static readonly System.Int32 kStorageCompanyEstimateLimit;
```


## Properties

- `public System.Int32 industrialCompanyDemand { get }`  

```csharp
public System.Int32 industrialCompanyDemand { get; }
```

- `public System.Int32 industrialBuildingDemand { get }`  

```csharp
public System.Int32 industrialBuildingDemand { get; }
```

- `public System.Int32 storageCompanyDemand { get }`  

```csharp
public System.Int32 storageCompanyDemand { get; }
```

- `public System.Int32 storageBuildingDemand { get }`  

```csharp
public System.Int32 storageBuildingDemand { get; }
```

- `public System.Int32 officeCompanyDemand { get }`  

```csharp
public System.Int32 officeCompanyDemand { get; }
```

- `public System.Int32 officeBuildingDemand { get }`  

```csharp
public System.Int32 officeBuildingDemand { get; }
```


## Constructors

- `public IndustrialDemandSystem()`  

```csharp
[Preserve]
	public IndustrialDemandSystem()
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

- `public GetBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetBuildingDemands(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_IndustrialBuildingDemands;
	}
```

- `public GetConsumption(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetConsumption(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_ResourceDemands;
	}
```

- `public GetIndustrialDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetIndustrialDemandFactors(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_IndustrialDemandFactors;
	}
```

- `public GetIndustrialResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetIndustrialResourceDemands(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_ResourceDemands;
	}
```

- `public GetOfficeDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetOfficeDemandFactors(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_OfficeDemandFactors;
	}
```

- `public GetResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetResourceDemands(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_IndustrialCompanyDemands;
	}
```

- `public GetStorageBuildingDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetStorageBuildingDemands(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_StorageBuildingDemands;
	}
```

- `public GetStorageCompanyDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetStorageCompanyDemands(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_StorageCompanyDemands;
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
		return 7;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_CountWorkplacesSystem = base.World.GetOrCreateSystemManaged<CountWorkplacesSystem>();
		m_CountCompanyDataSystem = base.World.GetOrCreateSystemManaged<CountCompanyDataSystem>();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_IndustrialQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Condemned>());
		m_OfficeQuery = GetEntityQuery(ComponentType.ReadOnly<OfficeProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Condemned>());
		m_StorageCompanyQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.Exclude<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ProcessDataQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.Exclude<ServiceCompanyData>());
		m_CityServiceQuery = GetEntityQuery(ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_UnlockedZoneDataQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneData>(), ComponentType.Exclude<Locked>());
		m_GameModeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		m_IndustrialCompanyDemand = new NativeValue<int>(Allocator.Persistent);
		m_IndustrialBuildingDemand = new NativeValue<int>(Allocator.Persistent);
		m_StorageCompanyDemand = new NativeValue<int>(Allocator.Persistent);
		m_StorageBuildingDemand = new NativeValue<int>(Allocator.Persistent);
		m_OfficeCompanyDemand = new NativeValue<int>(Allocator.Persistent);
		m_OfficeBuildingDemand = new NativeValue<int>(Allocator.Persistent);
		m_IndustrialDemandFactors = new NativeArray<int>(18, Allocator.Persistent);
		m_OfficeDemandFactors = new NativeArray<int>(18, Allocator.Persistent);
		int resourceCount = EconomyUtils.ResourceCount;
		m_IndustrialCompanyDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_IndustrialZoningDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_IndustrialBuildingDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_ResourceDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_StorageBuildingDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_StorageCompanyDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_FreeProperties = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_FreeStorages = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_Storages = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_StorageCapacities = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_IndustrialOfficeTaxEffectDemandOffset = 0f;
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
		m_IndustrialCompanyDemand.Dispose();
		m_IndustrialBuildingDemand.Dispose();
		m_StorageCompanyDemand.Dispose();
		m_StorageBuildingDemand.Dispose();
		m_OfficeCompanyDemand.Dispose();
		m_OfficeBuildingDemand.Dispose();
		m_IndustrialDemandFactors.Dispose();
		m_OfficeDemandFactors.Dispose();
		m_IndustrialCompanyDemands.Dispose();
		m_IndustrialZoningDemands.Dispose();
		m_IndustrialBuildingDemands.Dispose();
		m_StorageBuildingDemands.Dispose();
		m_StorageCompanyDemands.Dispose();
		m_ResourceDemands.Dispose();
		m_FreeProperties.Dispose();
		m_Storages.Dispose();
		m_FreeStorages.Dispose();
		m_StorageCapacities.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_ResourceDemands.Fill(0);
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			m_IndustrialOfficeTaxEffectDemandOffset = 0f;
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable)
		{
			m_IndustrialOfficeTaxEffectDemandOffset = singleton.m_IndustrialOfficeTaxEffectDemandOffset;
		}
		else
		{
			m_IndustrialOfficeTaxEffectDemandOffset = 0f;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_DemandParameterQuery.IsEmptyIgnoreFilter && !m_EconomyParameterQuery.IsEmptyIgnoreFilter)
		{
			m_LastIndustrialCompanyDemand = m_IndustrialCompanyDemand.value;
			m_LastIndustrialBuildingDemand = m_IndustrialBuildingDemand.value;
			m_LastStorageCompanyDemand = m_StorageCompanyDemand.value;
			m_LastStorageBuildingDemand = m_StorageBuildingDemand.value;
			m_LastOfficeCompanyDemand = m_OfficeCompanyDemand.value;
			m_LastOfficeBuildingDemand = m_OfficeBuildingDemand.value;
			JobHandle deps;
			CountCompanyDataSystem.IndustrialCompanyDatas industrialCompanyDatas = m_CountCompanyDataSystem.GetIndustrialCompanyDatas(out deps);
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			JobHandle outJobHandle3;
			JobHandle outJobHandle4;
			UpdateIndustrialDemandJob jobData = new UpdateIndustrialDemandJob
			{
				m_IndustrialPropertyChunks = m_IndustrialQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_OfficePropertyChunks = m_OfficeQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_StorageCompanyChunks = m_StorageCompanyQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle3),
				m_CityServiceChunks = m_CityServiceQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle4),
				m_UnlockedZoneDatas = m_UnlockedZoneDataQuery.ToComponentDataArray<ZoneData>(Allocator.TempJob),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ServiceUpkeepType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_City_CityServiceUpkeep_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PropertyOnMarketType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StorageLimitDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Attached = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceUpkeeps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_Upkeeps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
				m_DemandParameters = m_DemandParameterQuery.GetSingleton<DemandParameterData>(),
				m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
				m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
				m_EmployableByEducation = m_CountHouseholdDataSystem.GetEmployables(),
				m_TaxRates = m_TaxSystem.GetTaxRates(),
				m_FreeWorkplaces = m_CountWorkplacesSystem.GetFreeWorkplaces(),
				m_City = m_CitySystem.City,
				m_IndustrialCompanyDemand = m_IndustrialCompanyDemand,
				m_IndustrialBuildingDemand = m_IndustrialBuildingDemand,
				m_StorageCompanyDemand = m_StorageCompanyDemand,
				m_StorageBuildingDemand = m_StorageBuildingDemand,
				m_OfficeCompanyDemand = m_OfficeCompanyDemand,
				m_OfficeBuildingDemand = m_OfficeBuildingDemand,
				m_IndustrialCompanyDemands = m_IndustrialCompanyDemands,
				m_IndustrialBuildingDemands = m_IndustrialBuildingDemands,
				m_StorageBuildingDemands = m_StorageBuildingDemands,
				m_StorageCompanyDemands = m_StorageCompanyDemands,
				m_Propertyless = industrialCompanyDatas.m_ProductionPropertyless,
				m_CompanyResourceDemands = industrialCompanyDatas.m_Demand,
				m_FreeProperties = m_FreeProperties,
				m_Productions = industrialCompanyDatas.m_Production,
				m_Storages = m_Storages,
				m_FreeStorages = m_FreeStorages,
				m_StorageCapacities = m_StorageCapacities,
				m_IndustrialDemandFactors = m_IndustrialDemandFactors,
				m_OfficeDemandFactors = m_OfficeDemandFactors,
				m_ResourceDemands = m_ResourceDemands,
				m_IndustrialOfficeTaxEffectDemandOffset = m_IndustrialOfficeTaxEffectDemandOffset
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, m_ReadDependencies, outJobHandle, outJobHandle2, deps, outJobHandle3, outJobHandle4));
			m_WriteDependencies = base.Dependency;
			m_CountCompanyDataSystem.AddReader(base.Dependency);
			m_ResourceSystem.AddPrefabsReader(base.Dependency);
			m_TaxSystem.AddReader(base.Dependency);
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
		m_IndustrialCompanyDemand.value = 0;
		m_IndustrialBuildingDemand.value = 0;
		m_StorageCompanyDemand.value = 0;
		m_StorageBuildingDemand.value = 0;
		m_OfficeCompanyDemand.value = 0;
		m_OfficeBuildingDemand.value = 0;
		m_IndustrialDemandFactors.Fill(0);
		m_OfficeDemandFactors.Fill(0);
		m_IndustrialCompanyDemands.Fill(0);
		m_IndustrialZoningDemands.Fill(0);
		m_IndustrialBuildingDemands.Fill(0);
		m_StorageBuildingDemands.Fill(0);
		m_StorageCompanyDemands.Fill(0);
		m_FreeProperties.Fill(0);
		m_Storages.Fill(0);
		m_FreeStorages.Fill(0);
		m_LastIndustrialCompanyDemand = 0;
		m_LastIndustrialBuildingDemand = 0;
		m_LastStorageCompanyDemand = 0;
		m_LastStorageBuildingDemand = 0;
		m_LastOfficeCompanyDemand = 0;
		m_LastOfficeBuildingDemand = 0;
	}
```


## Nested types

- `Game.Simulation.IndustrialDemandSystem+UpdateIndustrialDemandJob`  
- `Game.Simulation.IndustrialDemandSystem+TypeHandle`  

