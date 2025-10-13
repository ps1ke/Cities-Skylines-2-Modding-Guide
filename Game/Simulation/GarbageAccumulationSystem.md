# Game.Simulation.GarbageAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageAccumulationSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_GarbageProducerQuery;
    private Unity.Entities.EntityArchetype m_CollectionRequestArchetype;
    private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation;
    private Unity.Jobs.JobHandle m_AccumulationDeps;
    private System.Int64 m_Accumulation;
    private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2138252455_0;
    private Unity.Entities.EntityQuery __query_2138252455_1;
    public static readonly System.Int32 kUpdatesPerDay;

    public System.Int64 garbageAccumulation { get; }

    public GarbageAccumulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public static System.Void GetGarbage(Game.Prefabs.ConsumptionData& consumption, Unity.Entities.Entity building, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHouseholds, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> currentDistricts, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.GarbageParameterData& garbageParameter);
    public static System.Void GetGarbageAccumulation(Unity.Entities.Entity building, Unity.Entities.Entity prefab, Game.Prefabs.ConsumptionData& consumption, Game.Areas.CurrentDistrict currentDistrict, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHousehold, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Game.Prefabs.GarbageParameterData& garbageParameter);
    public static System.Single GetGarbageEfficiencyFactor(System.Int32 garbage, Game.Prefabs.GarbageParameterData garbageParameters, System.Single maxPenalty);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_GarbageProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageProducerQuery;
```

- `private Unity.Entities.EntityArchetype m_CollectionRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_CollectionRequestArchetype;
```

- `private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation`  

```csharp
private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation;
```

- `private Unity.Jobs.JobHandle m_AccumulationDeps`  

```csharp
private Unity.Jobs.JobHandle m_AccumulationDeps;
```

- `private System.Int64 m_Accumulation`  

```csharp
private System.Int64 m_Accumulation;
```

- `private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2138252455_0`  

```csharp
private Unity.Entities.EntityQuery __query_2138252455_0;
```

- `private Unity.Entities.EntityQuery __query_2138252455_1`  

```csharp
private Unity.Entities.EntityQuery __query_2138252455_1;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public System.Int64 garbageAccumulation { get }`  

```csharp
public System.Int64 garbageAccumulation { get; }
```


## Constructors

- `public GarbageAccumulationSystem()`  

```csharp
[Preserve]
	public GarbageAccumulationSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<GarbageParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2138252455_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2138252455_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static GetGarbage(Game.Prefabs.ConsumptionData& consumption, Unity.Entities.Entity building, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHouseholds, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> currentDistricts, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.GarbageParameterData& garbageParameter) : System.Void`  

```csharp
public static void GetGarbage(ref ConsumptionData consumption, Entity building, Entity prefab, BufferLookup<Renter> renters, BufferLookup<Game.Buildings.Student> students, BufferLookup<Occupant> occupants, ComponentLookup<HomelessHousehold> homelessHouseholds, BufferLookup<HouseholdCitizen> householdCitizens, ComponentLookup<Citizen> citizens, BufferLookup<Employee> employees, BufferLookup<Patient> patients, ComponentLookup<SpawnableBuildingData> spawnableDatas, ComponentLookup<CurrentDistrict> currentDistricts, BufferLookup<DistrictModifier> districtModifiers, ComponentLookup<ZoneData> zoneDatas, DynamicBuffer<CityModifier> cityModifiers, ref GarbageParameterData garbageParameter)
	{
		CurrentDistrict currentDistrict = currentDistricts[building];
		GetGarbageAccumulation(building, prefab, ref consumption, currentDistrict, cityModifiers, citizens, spawnableDatas, zoneDatas, homelessHouseholds, householdCitizens, renters, employees, students, occupants, patients, districtModifiers, ref garbageParameter);
	}
```

- `public static GetGarbageAccumulation(Unity.Entities.Entity building, Unity.Entities.Entity prefab, Game.Prefabs.ConsumptionData& consumption, Game.Areas.CurrentDistrict currentDistrict, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHousehold, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Game.Prefabs.GarbageParameterData& garbageParameter) : System.Void`  

```csharp
public static void GetGarbageAccumulation(Entity building, Entity prefab, ref ConsumptionData consumption, CurrentDistrict currentDistrict, DynamicBuffer<CityModifier> cityModifiers, ComponentLookup<Citizen> citizens, ComponentLookup<SpawnableBuildingData> spawnableDatas, ComponentLookup<ZoneData> zoneDatas, ComponentLookup<HomelessHousehold> homelessHousehold, BufferLookup<HouseholdCitizen> householdCitizens, BufferLookup<Renter> renters, BufferLookup<Employee> employees, BufferLookup<Game.Buildings.Student> students, BufferLookup<Occupant> occupants, BufferLookup<Patient> patients, BufferLookup<DistrictModifier> districtModifiers, ref GarbageParameterData garbageParameter)
	{
		float num = 0f;
		int num2 = 0;
		float num3 = 0f;
		if (renters.HasBuffer(building))
		{
			DynamicBuffer<Renter> dynamicBuffer = renters[building];
			for (int i = 0; i < dynamicBuffer.Length; i++)
			{
				Entity renter = dynamicBuffer[i].m_Renter;
				if (householdCitizens.HasBuffer(renter))
				{
					DynamicBuffer<HouseholdCitizen> dynamicBuffer2 = householdCitizens[renter];
					if (homelessHousehold.HasComponent(renter))
					{
						num2 += dynamicBuffer2.Length;
						continue;
					}
					for (int j = 0; j < dynamicBuffer2.Length; j++)
					{
						Entity citizen = dynamicBuffer2[j].m_Citizen;
						if (citizens.HasComponent(citizen))
						{
							num3 += (float)citizens[citizen].GetEducationLevel();
							num += 1f;
						}
					}
				}
				else
				{
					if (!employees.HasBuffer(renter))
					{
						continue;
					}
					DynamicBuffer<Employee> dynamicBuffer3 = employees[renter];
					for (int k = 0; k < dynamicBuffer3.Length; k++)
					{
						Entity worker = dynamicBuffer3[k].m_Worker;
						if (citizens.HasComponent(worker))
						{
							num3 += (float)citizens[worker].GetEducationLevel();
							num += 1f;
						}
					}
				}
			}
			if (employees.HasBuffer(building))
			{
				DynamicBuffer<Employee> dynamicBuffer4 = employees[building];
				for (int l = 0; l < dynamicBuffer4.Length; l++)
				{
					Entity worker2 = dynamicBuffer4[l].m_Worker;
					if (citizens.HasComponent(worker2))
					{
						num3 += (float)citizens[worker2].GetEducationLevel();
						num += 1f;
					}
				}
			}
		}
		else
		{
			if (employees.HasBuffer(building))
			{
				DynamicBuffer<Employee> dynamicBuffer5 = employees[building];
				for (int m = 0; m < dynamicBuffer5.Length; m++)
				{
					Entity worker3 = dynamicBuffer5[m].m_Worker;
					if (citizens.HasComponent(worker3))
					{
						num3 += (float)citizens[worker3].GetEducationLevel();
						num += 1f;
					}
				}
			}
			if (students.HasBuffer(building))
			{
				DynamicBuffer<Game.Buildings.Student> dynamicBuffer6 = students[building];
				for (int n = 0; n < dynamicBuffer6.Length; n++)
				{
					Entity entity = dynamicBuffer6[n];
					if (citizens.HasComponent(entity))
					{
						num3 += (float)citizens[entity].GetEducationLevel();
						num += 1f;
					}
				}
			}
			if (occupants.HasBuffer(building))
			{
				DynamicBuffer<Occupant> dynamicBuffer7 = occupants[building];
				for (int num4 = 0; num4 < dynamicBuffer7.Length; num4++)
				{
					Entity entity2 = dynamicBuffer7[num4];
					if (citizens.HasComponent(entity2))
					{
						num3 += (float)citizens[entity2].GetEducationLevel();
						num += 1f;
					}
				}
			}
			if (patients.HasBuffer(building))
			{
				DynamicBuffer<Patient> dynamicBuffer8 = patients[building];
				for (int num5 = 0; num5 < dynamicBuffer8.Length; num5++)
				{
					Entity patient = dynamicBuffer8[num5].m_Patient;
					if (citizens.HasComponent(patient))
					{
						num3 += (float)citizens[patient].GetEducationLevel();
						num += 1f;
					}
				}
			}
		}
		float num6 = 0f;
		if (spawnableDatas.HasComponent(prefab))
		{
			num6 = (int)spawnableDatas[prefab].m_Level;
		}
		float num7 = 0f;
		num7 = ((!(num > 0f)) ? (consumption.m_GarbageAccumulation - num6 * garbageParameter.m_BuildingLevelBalance) : (math.max(0f, consumption.m_GarbageAccumulation - (num6 * garbageParameter.m_BuildingLevelBalance + num3 / num * garbageParameter.m_EducationBalance)) * num));
		if (num2 > 0)
		{
			num7 += (float)(garbageParameter.m_HomelessGarbageProduce * num2);
		}
		if (districtModifiers.HasBuffer(currentDistrict.m_District))
		{
			DynamicBuffer<DistrictModifier> modifiers = districtModifiers[currentDistrict.m_District];
			AreaUtils.ApplyModifier(ref num7, modifiers, DistrictModifierType.GarbageProduction);
		}
		if (spawnableDatas.HasComponent(prefab))
		{
			SpawnableBuildingData spawnableBuildingData = spawnableDatas[prefab];
			if (zoneDatas.HasComponent(spawnableBuildingData.m_ZonePrefab) && zoneDatas[spawnableBuildingData.m_ZonePrefab].m_AreaType == Game.Zones.AreaType.Industrial && (zoneDatas[spawnableBuildingData.m_ZonePrefab].m_ZoneFlags & ZoneFlags.Office) == 0)
			{
				CityUtils.ApplyModifier(ref num7, cityModifiers, CityModifierType.IndustrialGarbage);
			}
		}
		consumption.m_GarbageAccumulation = num7;
	}
```

- `public static GetGarbageEfficiencyFactor(System.Int32 garbage, Game.Prefabs.GarbageParameterData garbageParameters, System.Single maxPenalty) : System.Single`  

```csharp
public static float GetGarbageEfficiencyFactor(int garbage, GarbageParameterData garbageParameters, float maxPenalty)
	{
		float num = math.saturate((float)(garbage - garbageParameters.m_WarningGarbageLimit) / (float)(garbageParameters.m_MaxGarbageAccumulation - garbageParameters.m_WarningGarbageLimit));
		return 1f - maxPenalty * num;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_GarbageAccumulation = new NativeArray<long>(16, Allocator.Persistent);
		m_GarbageProducerQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<GarbageProducer>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_CollectionRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<GarbageCollectionRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireForUpdate(m_GarbageProducerQuery);
		RequireForUpdate<GarbageParameterData>();
		RequireForUpdate<BuildingEfficiencyParameterData>();
		Assert.IsTrue((long)(262144 / kUpdatesPerDay) >= 512L);
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
		m_GarbageAccumulation.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		m_AccumulationDeps.Complete();
		long num = 0L;
		for (int i = 0; i < 16; i++)
		{
			num += m_GarbageAccumulation[i];
		}
		m_Accumulation = num;
		m_GarbageAccumulation[(int)updateFrame] = 0L;
		GarbageParameterData singleton = __query_2138252455_0.GetSingleton<GarbageParameterData>();
		if (!base.EntityManager.HasEnabledComponent<Locked>(singleton.m_GarbageServicePrefab))
		{
			m_GarbageProducerQuery.ResetFilter();
			m_GarbageProducerQuery.SetSharedComponentFilter(new UpdateFrame(updateFrame));
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new GarbageAccumulationJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_GarbageProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageProducer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_GarbageCollectionRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_GarbageCollectionRequest_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
				m_QuantityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Quantity_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConsumptionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HomelessHousehold = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
				m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
				m_Students = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Student_RO_BufferLookup, ref base.CheckedStateRef),
				m_Occupants = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Occupant_RO_BufferLookup, ref base.CheckedStateRef),
				m_Patients = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Patient_RO_BufferLookup, ref base.CheckedStateRef),
				m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_City = m_CitySystem.City,
				m_UpdateFrame = (int)updateFrame,
				m_RandomSeed = RandomSeed.Next(),
				m_CollectionRequestArchetype = m_CollectionRequestArchetype,
				m_GarbageParameters = singleton,
				m_GarbageEfficiencyPenalty = __query_2138252455_1.GetSingleton<BuildingEfficiencyParameterData>().m_GarbagePenalty,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
				m_GarbageAccumulation = m_GarbageAccumulation
			}, m_GarbageProducerQuery, base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
			base.Dependency = jobHandle;
			m_AccumulationDeps = jobHandle;
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_Accumulation = 0L;
		for (int i = 0; i < m_GarbageAccumulation.Length; i++)
		{
			m_GarbageAccumulation[i] = 0L;
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
		m_Accumulation = 0L;
		for (int i = 0; i < m_GarbageAccumulation.Length; i++)
		{
			m_GarbageAccumulation[i] = 0L;
		}
	}
```


## Nested types

- `Game.Simulation.GarbageAccumulationSystem+GarbageAccumulationJob`  
- `Game.Simulation.GarbageAccumulationSystem+TypeHandle`  

