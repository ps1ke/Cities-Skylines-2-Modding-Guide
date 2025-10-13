# Game.Debug.EconomyDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EconomyDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_AgentQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Debug.BaseDebugSystem+Option m_ResidentialOption;
    private Game.Debug.BaseDebugSystem+Option m_CommercialOption;
    private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption;
    private Game.Debug.BaseDebugSystem+Option m_IndustrialOption;
    private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption;
    private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption;
    private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption;
    private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption;
    private Game.Debug.BaseDebugSystem+Option m_TradeCostOption;
    private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle;

    public EconomyDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void PrintAgeDebug();
    public static System.Void PrintCompanyDebug(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
    public static System.Void PrintSchoolDebug();
    public static System.Void PrintTradeDebug(Game.Simulation.ITradeSystem tradeSystem, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public static System.Void RemoveExtraCompanies();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AgentQuery`  

```csharp
private Unity.Entities.EntityQuery m_AgentQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentialOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentialOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CommercialOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CommercialOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CommercialStorageOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_IndustrialOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_IndustrialOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_UntaxedIncomeOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StorageUsedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_HouseholdNeedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ProfitabilityOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_TradeCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_TradeCostOption;
```

- `private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.EconomyDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EconomyDebugSystem()`  

```csharp
[Preserve]
	public EconomyDebugSystem()
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
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_AgentQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Economy.Resources>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<PropertyRenter>()
			},
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<Household>(),
				ComponentType.ReadOnly<ServiceAvailable>(),
				ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(),
				ComponentType.ReadOnly<Game.Companies.StorageCompany>(),
				ComponentType.ReadOnly<Profitability>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Hidden>()
			}
		});
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		base.Enabled = false;
		RequireForUpdate(m_AgentQuery);
		RequireForUpdate(m_EconomyParameterQuery);
		m_ResidentialOption = AddOption("Residential worth", defaultEnabled: false);
		m_CommercialOption = AddOption("Commercial worth", defaultEnabled: false);
		m_IndustrialOption = AddOption("Industrial worth", defaultEnabled: false);
		m_UntaxedIncomeOption = AddOption("Untaxed income", defaultEnabled: false);
		m_StorageUsedOption = AddOption("Storage used", defaultEnabled: false);
		m_HouseholdNeedOption = AddOption("Household need", defaultEnabled: false);
		m_ProfitabilityOption = AddOption("Company Profitability", defaultEnabled: false);
		m_TradeCostOption = AddOption("Trade Cost Profitability", defaultEnabled: false);
		m_CommercialStorageOption = AddOption("Commercial storage", defaultEnabled: false);
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
		if (!m_AgentQuery.IsEmptyIgnoreFilter)
		{
			JobHandle dependencies;
			EconomyGizmoJob jobData = new EconomyGizmoJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TradeCostBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_RenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ServiceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ProcessingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ProcessingCompany_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StorageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ProfitabilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_Profitability_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CargoTransportstationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CargoTransportStation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HouseholdNeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdNeed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Trucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
				m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
				m_StorageDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StorageLimitDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResidentialOption = m_ResidentialOption.enabled,
				m_CommercialOption = m_CommercialOption.enabled,
				m_IndustrialOption = m_IndustrialOption.enabled,
				m_UntaxedIncomeOption = m_UntaxedIncomeOption.enabled,
				m_StorageUsedOption = m_StorageUsedOption.enabled,
				m_HouseholdNeedOption = m_HouseholdNeedOption.enabled,
				m_ProfitabilityOption = m_ProfitabilityOption.enabled,
				m_TradeCostOption = m_TradeCostOption.enabled,
				m_CommercialStorageOption = m_CommercialStorageOption.enabled,
				m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_AgentQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
			m_ResourceSystem.AddPrefabsReader(base.Dependency);
			m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
		}
	}
```

- `public static PrintAgeDebug() : System.Void`  

```csharp
public static void PrintAgeDebug()
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		EntityQuery entityQuery = entityManager.CreateEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<MovingAway>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<Deleted>());
		EntityQuery entityQuery2 = entityManager.CreateEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		TimeData singleton = entityManager.CreateEntityQuery(ComponentType.ReadOnly<TimeData>()).GetSingleton<TimeData>();
		entityQuery2.GetSingleton<TimeSettingsData>();
		NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.TempJob);
		int num = 0;
		int[] array = new int[240];
		int day = TimeSystem.GetDay(World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<SimulationSystem>().frameIndex, singleton);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			DynamicBuffer<HouseholdCitizen> buffer = entityManager.GetBuffer<HouseholdCitizen>(nativeArray[i], isReadOnly: true);
			for (int j = 0; j < buffer.Length; j++)
			{
				Entity citizen = buffer[j].m_Citizen;
				int num2 = day - entityManager.GetComponentData<Citizen>(citizen).m_BirthDay;
				array[num2]++;
				num = math.max(num, num2);
			}
		}
		nativeArray.Dispose();
		for (int k = 0; k < num; k++)
		{
			UnityEngine.Debug.Log(k + ": " + array[k]);
		}
	}
```

- `public static PrintCompanyDebug(Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Void`  

```csharp
public static void PrintCompanyDebug(ComponentLookup<ResourceData> resourceDatas)
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		EntityQuery entityQuery = entityManager.CreateEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.ReadOnly<ServiceCompanyData>(), ComponentType.ReadOnly<WorkplaceData>());
		EntityQuery entityQuery2 = entityManager.CreateEntityQuery(ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.ReadOnly<IndustrialCompanyData>(), ComponentType.ReadOnly<WorkplaceData>(), ComponentType.Exclude<StorageCompanyData>());
		ResourcePrefabs prefabs = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<ResourceSystem>().GetPrefabs();
		NativeArray<ServiceCompanyData> nativeArray = entityQuery.ToComponentDataArray<ServiceCompanyData>(Allocator.TempJob);
		NativeArray<IndustrialProcessData> nativeArray2 = entityQuery.ToComponentDataArray<IndustrialProcessData>(Allocator.TempJob);
		NativeArray<WorkplaceData> nativeArray3 = entityQuery.ToComponentDataArray<WorkplaceData>(Allocator.TempJob);
		NativeArray<IndustrialProcessData> nativeArray4 = entityQuery2.ToComponentDataArray<IndustrialProcessData>(Allocator.TempJob);
		NativeArray<WorkplaceData> nativeArray5 = entityQuery2.ToComponentDataArray<WorkplaceData>(Allocator.TempJob);
		NativeArray<Entity> nativeArray6 = entityQuery2.ToEntityArray(Allocator.TempJob);
		NativeArray<EconomyParameterData> nativeArray7 = entityManager.CreateEntityQuery(ComponentType.ReadOnly<EconomyParameterData>()).ToComponentDataArray<EconomyParameterData>(Allocator.TempJob);
		EconomyParameterData economyParameters = nativeArray7[0];
		UnityEngine.Debug.Log("Company data per cell");
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ServiceCompanyData serviceCompanyData = nativeArray[i];
			IndustrialProcessData industrialProcessData = nativeArray2[i];
			BuildingData buildingData = new BuildingData
			{
				m_LotSize = new int2(100, 10)
			};
			ServiceAvailable serviceAvailable = new ServiceAvailable
			{
				m_MeanPriority = 0.5f
			};
			WorkplaceData workplaceData = nativeArray3[i];
			SpawnableBuildingData spawnableBuildingData = new SpawnableBuildingData
			{
				m_Level = 1
			};
			SpawnableBuildingData spawnableBuildingData2 = new SpawnableBuildingData
			{
				m_Level = 5
			};
			EconomyUtils.BuildPseudoTradeCost(5000f, industrialProcessData, ref resourceDatas, prefabs);
			string text = "C " + EconomyUtils.GetName(industrialProcessData.m_Output.m_Resource) + ": ";
			int workerAmount = Mathf.RoundToInt(serviceCompanyData.m_MaxWorkersPerCell * 1000f);
			int companyProductionPerDay = EconomyUtils.GetCompanyProductionPerDay(1f, workerAmount, spawnableBuildingData.m_Level, isIndustrial: true, workplaceData, industrialProcessData, prefabs, ref resourceDatas, ref economyParameters);
			int companyProductionPerDay2 = EconomyUtils.GetCompanyProductionPerDay(1f, workerAmount, spawnableBuildingData2.m_Level, isIndustrial: true, workplaceData, industrialProcessData, prefabs, ref resourceDatas, ref economyParameters);
			text = text + "Production " + (float)companyProductionPerDay / 1000f + "|" + (float)companyProductionPerDay2 / 1000f + ")";
			UnityEngine.Debug.Log(text);
		}
		for (int j = 0; j < nativeArray4.Length; j++)
		{
			IndustrialProcessData process = nativeArray4[j];
			BuildingData buildingData = new BuildingData
			{
				m_LotSize = new int2(100, 10)
			};
			EconomyUtils.BuildPseudoTradeCost(5000f, process, ref resourceDatas, prefabs);
			_ = nativeArray5[j];
			SpawnableBuildingData spawnableBuildingData3 = new SpawnableBuildingData
			{
				m_Level = 1
			};
			spawnableBuildingData3 = new SpawnableBuildingData
			{
				m_Level = 5
			};
			UnityEngine.Debug.Log("I " + EconomyUtils.GetName(process.m_Input1.m_Resource) + " => " + EconomyUtils.GetName(process.m_Output.m_Resource) + ": ");
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
		nativeArray3.Dispose();
		nativeArray6.Dispose();
		nativeArray4.Dispose();
		nativeArray5.Dispose();
		nativeArray7.Dispose();
	}
```

- `public static PrintSchoolDebug() : System.Void`  

```csharp
public static void PrintSchoolDebug()
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		EntityQuery entityQuery = entityManager.CreateEntityQuery(ComponentType.ReadOnly<Citizen>());
		int num = 0;
		int num2 = 0;
		NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (entityManager.TryGetComponent<Citizen>(nativeArray[i], out var component) && component.GetAge() == CitizenAge.Child)
			{
				num++;
				if (entityManager.GetComponentData<Citizen>(nativeArray[i]).GetEducationLevel() > 1)
				{
					UnityEngine.Debug.Log($"{nativeArray[i].Index} level ");
				}
				else
				{
					num2++;
				}
			}
		}
		UnityEngine.Debug.Log($"Processed {num} children, {num2} ok");
	}
```

- `public static PrintTradeDebug(Game.Simulation.ITradeSystem tradeSystem, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Void`  

```csharp
public static void PrintTradeDebug(ITradeSystem tradeSystem, DynamicBuffer<CityModifier> cityEffects)
	{
		ResourceIterator iterator = ResourceIterator.GetIterator();
		while (iterator.Next())
		{
			UnityEngine.Debug.Log(EconomyUtils.GetName(iterator.resource) + ":");
			UnityEngine.Debug.Log("Road: " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Road, import: true, cityEffects) + " / " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Road, import: false, cityEffects));
			UnityEngine.Debug.Log("Air: " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Air, import: true, cityEffects) + " / " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Air, import: false, cityEffects));
			UnityEngine.Debug.Log("Rail: " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Train, import: true, cityEffects) + " / " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Train, import: false, cityEffects));
			UnityEngine.Debug.Log("Ship: " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Ship, import: true, cityEffects) + " / " + tradeSystem.GetTradePrice(iterator.resource, OutsideConnectionTransferType.Ship, import: false, cityEffects));
		}
	}
```

- `public static RemoveExtraCompanies() : System.Void`  

```csharp
public static void RemoveExtraCompanies()
	{
		EntityManager entityManager = World.DefaultGameObjectInjectionWorld.EntityManager;
		EntityQuery entityQuery = entityManager.CreateEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<PropertyRenter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		entityManager.AddComponent<Deleted>(entityQuery);
	}
```


## Nested types

- `Game.Debug.EconomyDebugSystem+EconomyGizmoJob`  
- `Game.Debug.EconomyDebugSystem+TypeHandle`  

