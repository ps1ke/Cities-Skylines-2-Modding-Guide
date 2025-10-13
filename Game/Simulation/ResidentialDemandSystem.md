# Game.Simulation.ResidentialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResidentialDemandSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_DemandParameterGroup;
    private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand;
    private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand;
    private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Int32 m_LastHouseholdDemand;
    private Unity.Mathematics.int3 m_LastBuildingDemand;
    private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
    private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kMaxFactorEffect;

    public System.Int32 householdDemand { get; }
    public Unity.Mathematics.int3 buildingDemand { get; }

    public ResidentialDemandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetHighDensityDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetLowDensityDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetMediumDensityDemandFactors(Unity.Jobs.JobHandle& deps);
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

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem`  

```csharp
private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  

```csharp
private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_DemandParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterGroup;
```

- `private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand;
```

- `private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Int32 m_LastHouseholdDemand`  

```csharp
private System.Int32 m_LastHouseholdDemand;
```

- `private Unity.Mathematics.int3 m_LastBuildingDemand`  

```csharp
private Unity.Mathematics.int3 m_LastBuildingDemand;
```

- `private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector`  

```csharp
private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
```

- `private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kMaxFactorEffect`  

```csharp
public static readonly System.Int32 kMaxFactorEffect;
```


## Properties

- `public System.Int32 householdDemand { get }`  

```csharp
public System.Int32 householdDemand { get; }
```

- `public Unity.Mathematics.int3 buildingDemand { get }`  

```csharp
public Unity.Mathematics.int3 buildingDemand { get; }
```


## Constructors

- `public ResidentialDemandSystem()`  

```csharp
[Preserve]
	public ResidentialDemandSystem()
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

- `public GetHighDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetHighDensityDemandFactors(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_HighDemandFactors;
	}
```

- `public GetLowDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetLowDensityDemandFactors(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_LowDemandFactors;
	}
```

- `public GetMediumDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetMediumDensityDemandFactors(out JobHandle deps)
	{
		deps = m_WriteDependencies;
		return m_MediumDemandFactors;
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
		return 10;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_DemandParameterGroup = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_UnlockedZonePrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ZoneData>(), ComponentType.ReadOnly<ZonePropertiesData>(), ComponentType.Exclude<Locked>());
		m_GameModeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CountStudyPositionsSystem = base.World.GetOrCreateSystemManaged<CountStudyPositionsSystem>();
		m_CountWorkplacesSystem = base.World.GetOrCreateSystemManaged<CountWorkplacesSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_CountResidentialPropertySystem = base.World.GetOrCreateSystemManaged<CountResidentialPropertySystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_HouseholdDemand = new NativeValue<int>(Allocator.Persistent);
		m_BuildingDemand = new NativeValue<int3>(Allocator.Persistent);
		m_LowDemandFactors = new NativeArray<int>(18, Allocator.Persistent);
		m_MediumDemandFactors = new NativeArray<int>(18, Allocator.Persistent);
		m_HighDemandFactors = new NativeArray<int>(18, Allocator.Persistent);
		m_ResidentialDemandWeightsSelector = new float2(1f, 1f);
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
		m_HouseholdDemand.Dispose();
		m_BuildingDemand.Dispose();
		m_LowDemandFactors.Dispose();
		m_MediumDemandFactors.Dispose();
		m_HighDemandFactors.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			m_ResidentialDemandWeightsSelector = new float2(1f, 1f);
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable)
		{
			m_ResidentialDemandWeightsSelector = singleton.m_ResidentialDemandWeightsSelector;
		}
		else
		{
			m_ResidentialDemandWeightsSelector = new float2(1f, 1f);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_DemandParameterGroup.IsEmptyIgnoreFilter)
		{
			m_LastHouseholdDemand = m_HouseholdDemand.value;
			m_LastBuildingDemand = m_BuildingDemand.value;
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			JobHandle deps;
			UpdateResidentialDemandJob jobData = new UpdateResidentialDemandJob
			{
				m_UnlockedZonePrefabs = m_UnlockedZonePrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZonePropertiesDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DemandParameters = m_DemandParameterGroup.ToComponentDataListAsync<DemandParameterData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_StudyPositions = m_CountStudyPositionsSystem.GetStudyPositionsByEducation(out deps),
				m_FreeWorkplaces = m_CountWorkplacesSystem.GetFreeWorkplaces(),
				m_TotalWorkplaces = m_CountWorkplacesSystem.GetTotalWorkplaces(),
				m_HouseholdCountData = m_CountHouseholdDataSystem.GetHouseholdCountData(),
				m_ResidentialPropertyData = m_CountResidentialPropertySystem.GetResidentialPropertyData(),
				m_TaxRates = m_TaxSystem.GetTaxRates(),
				m_City = m_CitySystem.City,
				m_HouseholdDemand = m_HouseholdDemand,
				m_BuildingDemand = m_BuildingDemand,
				m_LowDemandFactors = m_LowDemandFactors,
				m_MediumDemandFactors = m_MediumDemandFactors,
				m_HighDemandFactors = m_HighDemandFactors,
				m_UnemploymentRate = m_CountHouseholdDataSystem.UnemploymentRate,
				m_ResidentialDemandWeightsSelector = m_ResidentialDemandWeightsSelector,
				m_TriggerQueue = m_TriggerSystem.CreateActionBuffer()
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, m_ReadDependencies, outJobHandle2, deps, outJobHandle));
			m_WriteDependencies = base.Dependency;
			m_CountStudyPositionsSystem.AddReader(base.Dependency);
			m_TaxSystem.AddReader(base.Dependency);
			m_TriggerSystem.AddActionBufferWriter(base.Dependency);
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
		m_HouseholdDemand.value = 0;
		m_BuildingDemand.value = default(int3);
		m_LowDemandFactors.Fill(0);
		m_MediumDemandFactors.Fill(0);
		m_HighDemandFactors.Fill(0);
		m_LastHouseholdDemand = 0;
		m_LastBuildingDemand = default(int3);
	}
```


## Nested types

- `Game.Simulation.ResidentialDemandSystem+UpdateResidentialDemandJob`  
- `Game.Simulation.ResidentialDemandSystem+TypeHandle`  

