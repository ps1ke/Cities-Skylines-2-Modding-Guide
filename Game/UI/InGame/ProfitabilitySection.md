# Game.UI.InGame.ProfitabilitySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProfitabilitySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
    private Unity.Entities.EntityQuery m_ProcessQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    public Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField;
    private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private Game.UI.InGame.CompanyProfitability profitability { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set; }

    public ProfitabilitySection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField`  

```csharp
private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField;
```

- `private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.CompanyProfitability profitability { private get; private set }`  

```csharp
private Game.UI.InGame.CompanyProfitability profitability { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set; }
```


## Constructors

- `public ProfitabilitySection()`  

```csharp
[Preserve]
	public ProfitabilitySection()
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
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_DistrictBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Renter>(), ComponentType.ReadOnly<CurrentDistrict>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ProcessQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_Factors = new NativeArray<int2>(28, Allocator.Persistent);
		profitabilityFactors = new NativeList<FactorInfo>(10, Allocator.Persistent);
		m_Results = new NativeArray<int>(3, Allocator.Persistent);
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
		m_Results.Dispose();
		m_Factors.Dispose();
		profitabilityFactors.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		int num = m_Results[1];
		int profit = ((num != 0) ? ((int)math.round((float)m_Results[2] / (float)num * 2f - 255f)) : 0);
		profitability = new CompanyProfitability(profit);
		for (int i = 0; i < m_Factors.Length; i++)
		{
			int x = m_Factors[i].x;
			if (x > 0)
			{
				float num2 = math.round((float)m_Factors[i].y / (float)x);
				if (num2 != 0f)
				{
					profitabilityFactors.Add(new FactorInfo(i, (int)num2));
				}
			}
		}
		profitabilityFactors.Sort();
		if (base.EntityManager.HasComponent<Building>(selectedEntity))
		{
			base.tooltipKeys.Add("Company");
		}
		else
		{
			base.tooltipKeys.Add("District");
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeArray<Entity> processes = m_ProcessQuery.ToEntityArray(Allocator.TempJob);
		EconomyParameterData singleton = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>();
		NativeArray<int> taxRates = m_TaxSystem.GetTaxRates();
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		if (base.EntityManager.HasComponent<District>(selectedEntity) && base.EntityManager.HasComponent<Area>(selectedEntity))
		{
			JobChunkExtensions.Schedule(new DistrictProfitabilityJob
			{
				m_SelectedEntity = selectedEntity,
				m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CitizenFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentDistrictHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AbandonedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ProfitabilityFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_Profitability_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RenterFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompanyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OfficeBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OfficeBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WorkProviderFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceAvailableFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingEfficiencyFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
				m_WorkplaceDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZonePropertyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceCompanyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceAvailabilityFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
				m_TradeCostFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_TradeCost_RO_BufferLookup, ref base.CheckedStateRef),
				m_EmployeeFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
				m_EconomyParameters = singleton,
				m_ResourcePrefabs = prefabs,
				m_TaxRates = taxRates,
				m_Processes = processes,
				m_Factors = m_Factors,
				m_Results = m_Results
			}, m_DistrictBuildingQuery, base.Dependency).Complete();
			base.visible = m_Results[0] > 0;
		}
		else
		{
			IJobExtensions.Schedule(new ProfitabilityJob
			{
				m_SelectedEntity = selectedEntity,
				m_SelectedPrefab = selectedPrefab,
				m_BuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ProfitabilityFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_Profitability_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AbandonedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CitizenFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RenterFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompanyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OfficeBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OfficeBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WorkProviderFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceAvailableFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingEfficiencyFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
				m_WorkplaceDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZonePropertyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceCompanyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceAvailabilityFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
				m_TradeCostFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_TradeCost_RO_BufferLookup, ref base.CheckedStateRef),
				m_EmployeeFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
				m_EconomyParameters = singleton,
				m_ResourcePrefabs = prefabs,
				m_TaxRates = taxRates,
				m_Processes = processes,
				m_Factors = m_Factors,
				m_Results = m_Results
			}, base.Dependency).Complete();
			base.visible = m_Results[0] > 0;
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("profitability");
		writer.Write(profitability);
		int num = math.min(10, profitabilityFactors.Length);
		writer.PropertyName("profitabilityFactors");
		writer.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			profitabilityFactors[i].WriteBuildingHappinessFactor(writer);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		for (int i = 0; i < m_Factors.Length; i++)
		{
			m_Factors[i] = 0;
		}
		profitability = default(CompanyProfitability);
		profitabilityFactors.Clear();
		m_Results[0] = 0;
		m_Results[1] = 0;
		m_Results[2] = 0;
	}
```


## Nested types

- `Game.UI.InGame.ProfitabilitySection+Result`  
- `Game.UI.InGame.ProfitabilitySection+ProfitabilityJob`  
- `Game.UI.InGame.ProfitabilitySection+DistrictProfitabilityJob`  
- `Game.UI.InGame.ProfitabilitySection+TypeHandle`  

