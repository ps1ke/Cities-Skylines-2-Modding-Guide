# Game.Simulation.HouseholdBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdBehaviorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private System.Single m_ResourceDemandPerCitizenMultiplier;
    private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kCarAmount;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMaxShoppingPossibility;
    public static readonly System.Int32 kMaxHouseholdNeedAmount;
    public static readonly System.Int32 kCarBuyingMinimumMoney;
    public static readonly System.Int32 KMinimumShoppingAmount;

    public HouseholdBehaviorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetAgeWeight(Game.Prefabs.ResourceData resourceData, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
    public static System.Single GetConsumptionMultiplier(Unity.Mathematics.float2 parameter, System.Int32 householdWealth);
    public static System.Boolean GetFreeCar(Unity.Entities.Entity household, Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> ownedVehicles, Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> personalCars, Unity.Entities.Entity& car);
    public static System.Int32 GetHighestEducation(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
    public static System.Single GetLastCommutePerCitizen(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Worker> workers);
    public static System.Int32 GetResourceShopWeightWithAge(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
    public static System.Int32 GetResourceShopWeightWithAge(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Int32 GetWeight(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded);
    public static System.Int32 GetWeight(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private System.Single m_ResourceDemandPerCitizenMultiplier`  

```csharp
private System.Single m_ResourceDemandPerCitizenMultiplier;
```

- `private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kCarAmount`  

```csharp
public static readonly System.Int32 kCarAmount;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMaxShoppingPossibility`  

```csharp
public static readonly System.Int32 kMaxShoppingPossibility;
```

- `public static readonly System.Int32 kMaxHouseholdNeedAmount`  

```csharp
public static readonly System.Int32 kMaxHouseholdNeedAmount;
```

- `public static readonly System.Int32 kCarBuyingMinimumMoney`  

```csharp
public static readonly System.Int32 kCarBuyingMinimumMoney;
```

- `public static readonly System.Int32 KMinimumShoppingAmount`  

```csharp
public static readonly System.Int32 KMinimumShoppingAmount;
```


## Constructors

- `public HouseholdBehaviorSystem()`  

```csharp
[Preserve]
	public HouseholdBehaviorSystem()
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

- `public static GetAgeWeight(Game.Prefabs.ResourceData resourceData, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  

```csharp
public static int GetAgeWeight(ResourceData resourceData, DynamicBuffer<HouseholdCitizen> citizens, ref ComponentLookup<Citizen> citizenDatas)
	{
		int num = 0;
		for (int i = 0; i < citizens.Length; i++)
		{
			Entity citizen = citizens[i].m_Citizen;
			num = citizenDatas[citizen].GetAge() switch
			{
				CitizenAge.Child => num + resourceData.m_ChildWeight, 
				CitizenAge.Teen => num + resourceData.m_TeenWeight, 
				CitizenAge.Elderly => num + resourceData.m_ElderlyWeight, 
				_ => num + resourceData.m_AdultWeight, 
			};
		}
		return num;
	}
```

- `public static GetConsumptionMultiplier(Unity.Mathematics.float2 parameter, System.Int32 householdWealth) : System.Single`  

```csharp
public static float GetConsumptionMultiplier(float2 parameter, int householdWealth)
	{
		return parameter.x + parameter.y * math.smoothstep(0f, 1f, (float)(math.max(0, householdWealth) + 1000) / 6000f);
	}
```

- `public static GetFreeCar(Unity.Entities.Entity household, Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> ownedVehicles, Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> personalCars, Unity.Entities.Entity& car) : System.Boolean`  

```csharp
public static bool GetFreeCar(Entity household, BufferLookup<OwnedVehicle> ownedVehicles, ComponentLookup<Game.Vehicles.PersonalCar> personalCars, ref Entity car)
	{
		if (ownedVehicles.HasBuffer(household))
		{
			DynamicBuffer<OwnedVehicle> dynamicBuffer = ownedVehicles[household];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				car = dynamicBuffer[i].m_Vehicle;
				if (personalCars.HasComponent(car) && personalCars[car].m_Keeper.Equals(Entity.Null))
				{
					return true;
				}
			}
		}
		car = Entity.Null;
		return false;
	}
```

- `public static GetHighestEducation(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Int32`  

```csharp
public static int GetHighestEducation(DynamicBuffer<HouseholdCitizen> citizenBuffer, ref ComponentLookup<Citizen> citizens)
	{
		int num = 0;
		for (int i = 0; i < citizenBuffer.Length; i++)
		{
			Entity citizen = citizenBuffer[i].m_Citizen;
			if (citizens.HasComponent(citizen))
			{
				Citizen citizen2 = citizens[citizen];
				CitizenAge age = citizen2.GetAge();
				if (age == CitizenAge.Teen || age == CitizenAge.Adult)
				{
					num = math.max(num, citizen2.GetEducationLevel());
				}
			}
		}
		return num;
	}
```

- `public static GetLastCommutePerCitizen(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Worker> workers) : System.Single`  

```csharp
public static float GetLastCommutePerCitizen(DynamicBuffer<HouseholdCitizen> householdCitizens, ComponentLookup<Worker> workers)
	{
		float num = 0f;
		float num2 = 0f;
		for (int i = 0; i < householdCitizens.Length; i++)
		{
			Entity citizen = householdCitizens[i].m_Citizen;
			if (workers.HasComponent(citizen))
			{
				num2 += workers[citizen].m_LastCommuteTime;
			}
			num += 1f;
		}
		return num2 / num;
	}
```

- `public static GetResourceShopWeightWithAge(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  

```csharp
public static int GetResourceShopWeightWithAge(int wealth, ResourceData resourceData, int carCount, bool leisureIncluded, DynamicBuffer<HouseholdCitizen> citizens, ref ComponentLookup<Citizen> citizenDatas)
	{
		float num = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_BaseConsumption : 0f);
		num += (float)(carCount * resourceData.m_CarConsumption);
		float xMin = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_WealthModifier : 0f);
		float num2 = GetAgeWeight(resourceData, citizens, ref citizenDatas);
		return Mathf.RoundToInt(100f * num2 * num * math.smoothstep(xMin, 1f, math.max(0.01f, ((float)wealth + 5000f) / 10000f)));
	}
```

- `public static GetResourceShopWeightWithAge(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  

```csharp
public static int GetResourceShopWeightWithAge(int wealth, ResourceData resourceData, int carCount, bool leisureIncluded, DynamicBuffer<HouseholdCitizen> citizens, ref ComponentLookup<Citizen> citizenDatas)
	{
		float num = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_BaseConsumption : 0f);
		num += (float)(carCount * resourceData.m_CarConsumption);
		float xMin = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_WealthModifier : 0f);
		float num2 = GetAgeWeight(resourceData, citizens, ref citizenDatas);
		return Mathf.RoundToInt(100f * num2 * num * math.smoothstep(xMin, 1f, math.max(0.01f, ((float)wealth + 5000f) / 10000f)));
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `public static GetWeight(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded) : System.Int32`  

```csharp
public static int GetWeight(int wealth, ResourceData resourceData, int carCount, bool leisureIncluded)
	{
		float num = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_BaseConsumption : 0f) + (float)(carCount * resourceData.m_CarConsumption);
		float xMin = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_WealthModifier : 0f);
		return Mathf.RoundToInt(num * math.smoothstep(xMin, 1f, math.clamp(((float)wealth + 5000f) / 10000f, 0.1f, 0.9f)));
	}
```

- `public static GetWeight(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded) : System.Int32`  

```csharp
public static int GetWeight(int wealth, ResourceData resourceData, int carCount, bool leisureIncluded)
	{
		float num = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_BaseConsumption : 0f) + (float)(carCount * resourceData.m_CarConsumption);
		float xMin = ((leisureIncluded || !resourceData.m_IsLeisure) ? resourceData.m_WealthModifier : 0f);
		return Mathf.RoundToInt(num * math.smoothstep(xMin, 1f, math.clamp(((float)wealth + 5000f) / 10000f, 0.1f, 0.9f)));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EconomyParameterGroup = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_HouseholdGroup = GetEntityQuery(ComponentType.ReadWrite<Household>(), ComponentType.ReadWrite<HouseholdNeed>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.ReadOnly<Game.Economy.Resources>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<MovingAway>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_GameModeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		m_ResourceDemandPerCitizenMultiplier = 1f;
		RequireForUpdate(m_HouseholdGroup);
		RequireForUpdate(m_EconomyParameterGroup);
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
			m_ResourceDemandPerCitizenMultiplier = 1f;
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable)
		{
			m_ResourceDemandPerCitizenMultiplier = singleton.m_ResourceDemandPerCitizenMultiplier;
		}
		else
		{
			m_ResourceDemandPerCitizenMultiplier = 1f;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		HouseholdTickJob jobData = new HouseholdTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdNeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdNeed_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TouristHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TouristHousehold_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommuterHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CommuterHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_LodgingSeekerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_LodgingSeeker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_RenterBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterGroup.GetSingleton<EconomyParameterData>(),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertySeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_PropertySeeker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LodgingProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_LodgingProvider_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConsumptionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_RandomSeed = RandomSeed.Next(),
			m_ResourceDemandPerCitizenMultiplier = m_ResourceDemandPerCitizenMultiplier,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_City = m_CitySystem.City
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HouseholdGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		m_TaxSystem.AddReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.HouseholdBehaviorSystem+HouseholdTickJob`  
- `Game.Simulation.HouseholdBehaviorSystem+TypeHandle`  

