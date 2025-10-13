# Game.UI.InGame.AverageHappinessSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AverageHappinessSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
    public Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.CitizenHappiness <averageHappiness>k__BackingField;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <happinessFactors>k__BackingField;
    protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    protected Unity.Entities.EntityQuery m_GarbageParameterQuery;
    protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
    protected Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    protected Unity.Entities.EntityQuery m_ParkParameterQuery;
    protected Unity.Entities.EntityQuery m_EducationParameterQuery;
    protected Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Game.UI.InGame.AverageHappinessSection+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1244325462_0;

    protected System.String group { protected get; }
    private Game.UI.InGame.CitizenHappiness averageHappiness { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> happinessFactors { private get; private set; }

    public AverageHappinessSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private static System.Boolean TryAddPropertyHappiness(System.Int32& happiness, System.Int32& citizenCount, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> healthProblemFromEntity, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterFromEntity, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizenFromEntity);
}
```


## Fields

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.CitizenHappiness <averageHappiness>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenHappiness <averageHappiness>k__BackingField;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <happinessFactors>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <happinessFactors>k__BackingField;
```

- `protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `private Game.UI.InGame.AverageHappinessSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.AverageHappinessSection+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1244325462_0`  

```csharp
private Unity.Entities.EntityQuery __query_1244325462_0;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.CitizenHappiness averageHappiness { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenHappiness averageHappiness { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> happinessFactors { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> happinessFactors { private get; private set; }
```


## Constructors

- `public AverageHappinessSection()`  

```csharp
[Preserve]
	public AverageHappinessSection()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ServiceFeeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1244325462_0 = entityQueryBuilder2.Build(ref state);
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
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_DistrictBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Renter>(), ComponentType.ReadOnly<CurrentDistrict>(), ComponentType.ReadOnly<ResidentialProperty>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CitizenHappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_GarbageParameterQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_HappinessFactorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HappinessFactorParameterData>());
		m_HealthcareParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_ParkParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ParkParameterData>());
		m_EducationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EducationParameterData>());
		m_TelecomParameterQuery = GetEntityQuery(ComponentType.ReadOnly<TelecomParameterData>());
		m_Factors = new NativeArray<int2>(28, Allocator.Persistent);
		happinessFactors = new NativeList<FactorInfo>(10, Allocator.Persistent);
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
		happinessFactors.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		int num = m_Results[1];
		int num2 = m_Results[2];
		averageHappiness = CitizenUIUtils.GetCitizenHappiness(num2 / math.select(num, 1, num == 0));
		for (int i = 0; i < m_Factors.Length; i++)
		{
			int x = m_Factors[i].x;
			if (x > 0)
			{
				float num3 = math.round((float)m_Factors[i].y / (float)x);
				if (num3 != 0f)
				{
					happinessFactors.Add(new FactorInfo(i, (int)num3));
				}
			}
		}
		happinessFactors.Sort();
		if (base.EntityManager.HasComponent<Building>(selectedEntity))
		{
			base.tooltipKeys.Add("Building");
		}
		else if (base.EntityManager.HasComponent<Household>(selectedEntity))
		{
			base.tooltipKeys.Add("Household");
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
		CitizenHappinessParameterData singleton = m_CitizenHappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>();
		GarbageParameterData singleton2 = m_GarbageParameterQuery.GetSingleton<GarbageParameterData>();
		DynamicBuffer<HappinessFactorParameterData> bufferAfterCompletingDependency = InternalCompilerInterface.GetBufferAfterCompletingDependency(ref __TypeHandle.__Game_Prefabs_HappinessFactorParameterData_RW_BufferLookup, ref base.CheckedStateRef, m_HappinessFactorParameterQuery.GetSingletonEntity());
		HealthcareParameterData singleton3 = m_HealthcareParameterQuery.GetSingleton<HealthcareParameterData>();
		ParkParameterData singleton4 = m_ParkParameterQuery.GetSingleton<ParkParameterData>();
		EducationParameterData singleton5 = m_EducationParameterQuery.GetSingleton<EducationParameterData>();
		TelecomParameterData singleton6 = m_TelecomParameterQuery.GetSingleton<TelecomParameterData>();
		ServiceFeeParameterData singleton7 = __query_1244325462_0.GetSingleton<ServiceFeeParameterData>();
		JobHandle dependencies;
		NativeArray<GroundPollution> buffer = m_GroundPollutionSystem.GetData(readOnly: true, out dependencies).m_Buffer;
		JobHandle dependencies2;
		NativeArray<NoisePollution> buffer2 = m_NoisePollutionSystem.GetData(readOnly: true, out dependencies2).m_Buffer;
		JobHandle dependencies3;
		NativeArray<AirPollution> buffer3 = m_AirPollutionSystem.GetData(readOnly: true, out dependencies3).m_Buffer;
		JobHandle dependencies4;
		CellMapData<TelecomCoverage> data = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies4);
		dependencies.Complete();
		dependencies2.Complete();
		dependencies3.Complete();
		dependencies4.Complete();
		NativeArray<int> taxRates = m_TaxSystem.GetTaxRates();
		DynamicBuffer<ServiceFee> buffer4 = base.EntityManager.GetBuffer<ServiceFee>(m_CitySystem.City);
		float relativeElectricityFee = ServiceFeeSystem.GetFee(PlayerResource.Electricity, buffer4) / singleton7.m_ElectricityFee.m_Default;
		float relativeWaterFee = ServiceFeeSystem.GetFee(PlayerResource.Water, buffer4) / singleton7.m_WaterFee.m_Default;
		if (base.EntityManager.HasComponent<District>(selectedEntity) && base.EntityManager.HasComponent<Area>(selectedEntity))
		{
			JobChunkExtensions.Schedule(new CountDistrictHappinessJob
			{
				m_SelectedEntity = selectedEntity,
				m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CitizenFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentDistrictHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AbandonedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizenFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_RenterFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConsumerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterConsumerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LockedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GarbageProducersFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CrimeProducersFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MailProducerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CityModifierFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ServiceCoverageFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
				m_CitizenHappinessParameters = singleton,
				m_GarbageParameters = singleton2,
				m_HealthcareParameters = singleton3,
				m_ParkParameters = singleton4,
				m_EducationParameters = singleton5,
				m_TelecomParameters = singleton6,
				m_HappinessFactorParameters = bufferAfterCompletingDependency,
				m_TelecomCoverage = data,
				m_PollutionMap = buffer,
				m_NoisePollutionMap = buffer2,
				m_AirPollutionMap = buffer3,
				m_TaxRates = taxRates,
				m_Factors = m_Factors,
				m_Results = m_Results,
				m_City = m_CitySystem.City,
				m_RelativeElectricityFee = relativeElectricityFee,
				m_RelativeWaterFee = relativeWaterFee
			}, m_DistrictBuildingQuery, base.Dependency).Complete();
			base.visible = m_Results[0] > 0;
		}
		else
		{
			IJobExtensions.Schedule(new CountHappinessJob
			{
				m_SelectedEntity = selectedEntity,
				m_BuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResidentialPropertyFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ResidentialProperty_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HealthProblemFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenterFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AbandonedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CitizenFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizenFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_RenterFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingPropertyDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConsumerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaterConsumerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LockedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GarbageProducersFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CrimeProducersFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MailProducerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CityModifierFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ServiceCoverageFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
				m_CitizenHappinessParameters = singleton,
				m_GarbageParameters = singleton2,
				m_HealthcareParameters = singleton3,
				m_ParkParameters = singleton4,
				m_EducationParameters = singleton5,
				m_TelecomParameters = singleton6,
				m_HappinessFactorParameters = bufferAfterCompletingDependency,
				m_TelecomCoverage = data,
				m_PollutionMap = buffer,
				m_NoisePollutionMap = buffer2,
				m_AirPollutionMap = buffer3,
				m_TaxRates = taxRates,
				m_Factors = m_Factors,
				m_Results = m_Results,
				m_City = m_CitySystem.City,
				m_RelativeElectricityFee = relativeElectricityFee,
				m_RelativeWaterFee = relativeWaterFee
			}, base.Dependency).Complete();
			base.visible = m_Results[0] > 0;
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("averageHappiness");
		writer.Write(averageHappiness);
		int num = math.min(10, happinessFactors.Length);
		writer.PropertyName("happinessFactors");
		writer.ArrayBegin(num);
		for (int i = 0; i < num; i++)
		{
			happinessFactors[i].WriteBuildingHappinessFactor(writer);
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
		averageHappiness = default(CitizenHappiness);
		happinessFactors.Clear();
		m_Results[0] = 0;
		m_Results[1] = 0;
		m_Results[2] = 0;
	}
```

- `private static TryAddPropertyHappiness(System.Int32& happiness, System.Int32& citizenCount, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> healthProblemFromEntity, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterFromEntity, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizenFromEntity) : System.Boolean`  

```csharp
private static bool TryAddPropertyHappiness(ref int happiness, ref int citizenCount, Entity entity, ComponentLookup<Household> householdFromEntity, ComponentLookup<Citizen> citizenFromEntity, ComponentLookup<HealthProblem> healthProblemFromEntity, BufferLookup<Renter> renterFromEntity, BufferLookup<HouseholdCitizen> householdCitizenFromEntity)
	{
		bool result = false;
		if (renterFromEntity.TryGetBuffer(entity, out var bufferData))
		{
			for (int i = 0; i < bufferData.Length; i++)
			{
				Entity renter = bufferData[i].m_Renter;
				if (!householdFromEntity.HasComponent(renter) || !householdCitizenFromEntity.TryGetBuffer(renter, out var bufferData2))
				{
					continue;
				}
				result = true;
				for (int j = 0; j < bufferData2.Length; j++)
				{
					Entity citizen = bufferData2[j].m_Citizen;
					if (citizenFromEntity.HasComponent(citizen) && !CitizenUtils.IsDead(citizen, ref healthProblemFromEntity))
					{
						happiness += citizenFromEntity[citizen].Happiness;
						citizenCount++;
					}
				}
			}
		}
		return result;
	}
```


## Nested types

- `Game.UI.InGame.AverageHappinessSection+Result`  
- `Game.UI.InGame.AverageHappinessSection+CountHappinessJob`  
- `Game.UI.InGame.AverageHappinessSection+CountDistrictHappinessJob`  
- `Game.UI.InGame.AverageHappinessSection+TypeHandle`  

