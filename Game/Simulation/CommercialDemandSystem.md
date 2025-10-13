# Game.Simulation.CommercialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommercialDemandSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Unity.Entities.EntityQuery m_CommercialQuery;
    private Unity.Entities.EntityQuery m_CommercialProcessDataQuery;
    private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand;
    private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand;
    private Unity.Collections.NativeArray<System.Int32> m_DemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
    private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands;
    private Unity.Collections.NativeArray<System.Int32> m_Consumption;
    private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Int32 m_LastCompanyDemand;
    private System.Int32 m_LastBuildingDemand;
    private System.Single m_CommercialTaxEffectDemandOffset;
    private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle;

    public System.Int32 companyDemand { get; }
    public System.Int32 buildingDemand { get; }

    public CommercialDemandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetBuildingDemands(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetConsumption(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetResourceDemands(Unity.Jobs.JobHandle& deps);
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

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialProcessDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialProcessDataQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZoneDataQuery;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_CompanyDemand;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_BuildingDemand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_DemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_DemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ResourceDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_BuildingDemands;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Consumption`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Consumption;
```

- `private Unity.Collections.NativeArray<System.Int32> m_FreeProperties`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_FreeProperties;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Int32 m_LastCompanyDemand`  

```csharp
private System.Int32 m_LastCompanyDemand;
```

- `private System.Int32 m_LastBuildingDemand`  

```csharp
private System.Int32 m_LastBuildingDemand;
```

- `private System.Single m_CommercialTaxEffectDemandOffset`  

```csharp
private System.Single m_CommercialTaxEffectDemandOffset;
```

- `private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommercialDemandSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 companyDemand { get }`  

```csharp
public System.Int32 companyDemand { get; }
```

- `public System.Int32 buildingDemand { get }`  

```csharp
public System.Int32 buildingDemand { get; }
```


## Constructors

- `public CommercialDemandSystem()`  

```csharp
[Preserve]
	public CommercialDemandSystem()
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
		return m_BuildingDemands;
	}
```

- `public GetConsumption(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetConsumption(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_Consumption;
	}
```

- `public GetDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetDemandFactors(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_DemandFactors;
	}
```

- `public GetResourceDemands(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetResourceDemands(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_ResourceDemands;
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
		return 4;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CountCompanyDataSystem = base.World.GetOrCreateSystemManaged<CountCompanyDataSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_CommercialQuery = GetEntityQuery(ComponentType.ReadOnly<CommercialProperty>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Condemned>(), ComponentType.Exclude<Temp>());
		m_CommercialProcessDataQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.ReadOnly<ServiceCompanyData>());
		m_UnlockedZoneDataQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneData>(), ComponentType.Exclude<Locked>());
		m_GameModeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		m_CompanyDemand = new NativeValue<int>(Allocator.Persistent);
		m_BuildingDemand = new NativeValue<int>(Allocator.Persistent);
		m_DemandFactors = new NativeArray<int>(18, Allocator.Persistent);
		int resourceCount = EconomyUtils.ResourceCount;
		m_ResourceDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_BuildingDemands = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_Consumption = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_FreeProperties = new NativeArray<int>(resourceCount, Allocator.Persistent);
		m_CommercialTaxEffectDemandOffset = 0f;
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_DemandParameterQuery);
		RequireForUpdate(m_CommercialProcessDataQuery);
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
		m_CompanyDemand.Dispose();
		m_BuildingDemand.Dispose();
		m_DemandFactors.Dispose();
		m_ResourceDemands.Dispose();
		m_BuildingDemands.Dispose();
		m_Consumption.Dispose();
		m_FreeProperties.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_Consumption.Fill(0);
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			m_CommercialTaxEffectDemandOffset = 0f;
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable)
		{
			m_CommercialTaxEffectDemandOffset = singleton.m_CommercialTaxEffectDemandOffset;
		}
		else
		{
			m_CommercialTaxEffectDemandOffset = 0f;
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
			m_LastCompanyDemand = m_CompanyDemand.value;
			m_LastBuildingDemand = m_BuildingDemand.value;
			JobHandle deps;
			CountCompanyDataSystem.CommercialCompanyDatas commercialCompanyDatas = m_CountCompanyDataSystem.GetCommercialCompanyDatas(out deps);
			JobHandle outJobHandle;
			UpdateCommercialDemandJob jobData = new UpdateCommercialDemandJob
			{
				m_CommercialPropertyChunks = m_CommercialQuery.ToArchetypeChunkListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_UnlockedZoneDatas = m_UnlockedZoneDataQuery.ToComponentDataArray<ZoneData>(Allocator.TempJob),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PropertyOnMarketType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommercialCompanies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CommercialCompany_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
				m_DemandParameters = m_DemandParameterQuery.GetSingleton<DemandParameterData>(),
				m_TaxRates = m_TaxSystem.GetTaxRates(),
				m_CompanyDemand = m_CompanyDemand,
				m_BuildingDemand = m_BuildingDemand,
				m_DemandFactors = m_DemandFactors,
				m_City = m_CitySystem.City,
				m_ResourceDemands = m_ResourceDemands,
				m_BuildingDemands = m_BuildingDemands,
				m_ProduceCapacity = commercialCompanyDatas.m_ProduceCapacity,
				m_CurrentAvailables = commercialCompanyDatas.m_CurrentAvailables,
				m_FreeProperties = m_FreeProperties,
				m_Propertyless = commercialCompanyDatas.m_ServicePropertyless,
				m_Tourisms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Tourism_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommercialTaxEffectDemandOffset = m_CommercialTaxEffectDemandOffset
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, m_ReadDependencies, outJobHandle, deps));
			m_WriteDependencies = base.Dependency;
			m_CountHouseholdDataSystem.AddHouseholdDataReader(base.Dependency);
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
		m_CompanyDemand.value = 0;
		m_BuildingDemand.value = 0;
		m_DemandFactors.Fill(0);
		m_ResourceDemands.Fill(0);
		m_BuildingDemands.Fill(0);
		m_Consumption.Fill(0);
		m_FreeProperties.Fill(0);
		m_LastCompanyDemand = 0;
		m_LastBuildingDemand = 0;
	}
```


## Nested types

- `Game.Simulation.CommercialDemandSystem+UpdateCommercialDemandJob`  
- `Game.Simulation.CommercialDemandSystem+TypeHandle`  

