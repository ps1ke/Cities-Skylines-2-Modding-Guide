# Game.Simulation.ServiceFeeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IServiceFeeSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceFeeSystem : Game.GameSystemBase, Game.Simulation.IServiceFeeSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FeeCollectorGroup;
    private Unity.Entities.EntityQuery m_CollectedFeeGroup;
    private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue;
    private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees;
    private Unity.Jobs.JobHandle m_Writers;
    private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdatesPerDay;

    public ServiceFeeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle deps);
    private System.Void CacheFees(System.Boolean reset);
    public System.Void Deserialize<TReader>(TReader reader);
    public static System.Single GetConsumptionMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
    public static Game.City.PlayerResource GetEducationResource(System.Int32 level);
    public static System.Single GetEfficiencyMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
    public static System.Single GetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees);
    public Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> GetFeeQueue(Unity.Jobs.JobHandle& deps);
    public static System.Int32 GetHappinessEffect(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& happinessParameters);
    public System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee);
    public static System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees);
    public Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> GetServiceFees();
    public Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource);
    public static Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public static System.Void SetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single value);
    public static System.Boolean TryGetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single& fee);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FeeCollectorGroup`  

```csharp
private Unity.Entities.EntityQuery m_FeeCollectorGroup;
```

- `private Unity.Entities.EntityQuery m_CollectedFeeGroup`  

```csharp
private Unity.Entities.EntityQuery m_CollectedFeeGroup;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue;
```

- `private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees;
```

- `private Unity.Jobs.JobHandle m_Writers`  

```csharp
private Unity.Jobs.JobHandle m_Writers;
```

- `private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public ServiceFeeSystem()`  

```csharp
[Preserve]
	public ServiceFeeSystem()
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

- `public AddQueueWriter(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public void AddQueueWriter(JobHandle deps)
	{
		m_Writers = JobHandle.CombineDependencies(m_Writers, deps);
	}
```

- `private CacheFees(System.Boolean reset = False) : System.Void`  

```csharp
private void CacheFees(bool reset = false)
	{
		NativeArray<Entity> nativeArray = m_CollectedFeeGroup.ToEntityArray(Allocator.TempJob);
		m_CityServiceFees.Clear();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			DynamicBuffer<CollectedCityServiceFeeData> buffer = base.EntityManager.GetBuffer<CollectedCityServiceFeeData>(entity, !reset);
			for (int j = 0; j < buffer.Length; j++)
			{
				if (reset)
				{
					CollectedCityServiceFeeData value = new CollectedCityServiceFeeData
					{
						m_PlayerResource = buffer[j].m_PlayerResource
					};
					buffer[j] = value;
				}
				m_CityServiceFees.Add(buffer[j]);
			}
		}
		nativeArray.Dispose();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static GetConsumptionMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters) : System.Single`  

```csharp
public static float GetConsumptionMultiplier(PlayerResource resource, float relativeFee, in ServiceFeeParameterData feeParameters)
	{
		return resource switch
		{
			PlayerResource.Electricity => AdjustElectricityConsumptionSystem.GetFeeConsumptionMultiplier(relativeFee, in feeParameters), 
			PlayerResource.Water => AdjustWaterConsumptionSystem.GetFeeConsumptionMultiplier(relativeFee, in feeParameters), 
			_ => 1f, 
		};
	}
```

- `public static GetEducationResource(System.Int32 level) : Game.City.PlayerResource`  

```csharp
public static PlayerResource GetEducationResource(int level)
	{
		switch (level)
		{
		case 1:
			return PlayerResource.BasicEducation;
		case 2:
			return PlayerResource.SecondaryEducation;
		case 3:
		case 4:
			return PlayerResource.HigherEducation;
		default:
			return PlayerResource.Count;
		}
	}
```

- `public static GetEfficiencyMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters) : System.Single`  

```csharp
public static float GetEfficiencyMultiplier(PlayerResource resource, float relativeFee, in BuildingEfficiencyParameterData efficiencyParameters)
	{
		return resource switch
		{
			PlayerResource.Electricity => AdjustElectricityConsumptionSystem.GetFeeEfficiencyFactor(relativeFee, in efficiencyParameters), 
			PlayerResource.Water => AdjustWaterConsumptionSystem.GetFeeEfficiencyFactor(relativeFee, in efficiencyParameters), 
			_ => 1f, 
		};
	}
```

- `public static GetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees) : System.Single`  

```csharp
public static float GetFee(PlayerResource resource, DynamicBuffer<ServiceFee> fees)
	{
		for (int i = 0; i < fees.Length; i++)
		{
			ServiceFee serviceFee = fees[i];
			if (serviceFee.m_Resource == resource)
			{
				return serviceFee.m_Fee;
			}
		}
		return 0f;
	}
```

- `public GetFeeQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent>`  

```csharp
public NativeQueue<FeeEvent> GetFeeQueue(out JobHandle deps)
	{
		deps = m_Writers;
		return m_FeeQueue;
	}
```

- `public static GetHappinessEffect(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& happinessParameters) : System.Int32`  

```csharp
public static int GetHappinessEffect(PlayerResource resource, float relativeFee, in CitizenHappinessParameterData happinessParameters)
	{
		return resource switch
		{
			PlayerResource.Electricity => CitizenHappinessSystem.GetElectricityFeeHappinessEffect(relativeFee, in happinessParameters), 
			PlayerResource.Water => CitizenHappinessSystem.GetWaterFeeHappinessEffect(relativeFee, in happinessParameters), 
			_ => 1, 
		};
	}
```

- `public GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee) : System.Int32`  

```csharp
public static int GetServiceFeeIncomeEstimate(PlayerResource resource, float fee, NativeList<CollectedCityServiceFeeData> fees)
	{
		float num = 0f;
		foreach (CollectedCityServiceFeeData item in fees)
		{
			if (item.m_PlayerResource == (int)resource)
			{
				num += item.m_InternalCount * fee;
			}
		}
		return (int)math.round(num);
	}
```

- `public static GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees) : System.Int32`  

```csharp
public static int GetServiceFeeIncomeEstimate(PlayerResource resource, float fee, NativeList<CollectedCityServiceFeeData> fees)
	{
		float num = 0f;
		foreach (CollectedCityServiceFeeData item in fees)
		{
			if (item.m_PlayerResource == (int)resource)
			{
				num += item.m_InternalCount * fee;
			}
		}
		return (int)math.round(num);
	}
```

- `public GetServiceFees() : Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData>`  

```csharp
public static int3 GetServiceFees(PlayerResource resource, NativeList<CollectedCityServiceFeeData> fees)
	{
		float3 x = default(float3);
		foreach (CollectedCityServiceFeeData item in fees)
		{
			if (item.m_PlayerResource == (int)resource)
			{
				x += new float3(item.m_Internal, item.m_Export, item.m_Import);
			}
		}
		return new int3(math.round(x));
	}
```

- `public GetServiceFees(Game.City.PlayerResource resource) : Unity.Mathematics.int3`  

```csharp
public static int3 GetServiceFees(PlayerResource resource, NativeList<CollectedCityServiceFeeData> fees)
	{
		float3 x = default(float3);
		foreach (CollectedCityServiceFeeData item in fees)
		{
			if (item.m_PlayerResource == (int)resource)
			{
				x += new float3(item.m_Internal, item.m_Export, item.m_Import);
			}
		}
		return new int3(math.round(x));
	}
```

- `public static GetServiceFees(Game.City.PlayerResource resource, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees) : Unity.Mathematics.int3`  

```csharp
public static int3 GetServiceFees(PlayerResource resource, NativeList<CollectedCityServiceFeeData> fees)
	{
		float3 x = default(float3);
		foreach (CollectedCityServiceFeeData item in fees)
		{
			if (item.m_PlayerResource == (int)resource)
			{
				x += new float3(item.m_Internal, item.m_Export, item.m_Import);
			}
		}
		return new int3(math.round(x));
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 2048;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CollectedFeeGroup = GetEntityQuery(ComponentType.ReadOnly<CollectedCityServiceFeeData>());
		m_FeeCollectorGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.City.ServiceFeeCollector>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Patient>(),
				ComponentType.ReadOnly<Game.Buildings.Student>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_CollectedFeeGroup);
		m_FeeQueue = new NativeQueue<FeeEvent>(Allocator.Persistent);
		m_CityServiceFees = new NativeList<CollectedCityServiceFeeData>(13, Allocator.Persistent);
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
		m_Writers.Complete();
		m_FeeQueue.Dispose();
		m_CityServiceFees.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		CacheFees();
		PayFeeJob jobData = new PayFeeJob
		{
			m_PatientType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Patient_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Student_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Fees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RW_BufferLookup, ref base.CheckedStateRef),
			m_FeeEvents = m_FeeQueue,
			m_City = m_CitySystem.City
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_FeeCollectorGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		JobHandle outJobHandle;
		FeeToCityJob jobData2 = new FeeToCityJob
		{
			m_FeeDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceFeeData_RW_BufferLookup, ref base.CheckedStateRef),
			m_FeeDataEntities = m_CollectedFeeGroup.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_FeeEvents = m_FeeQueue,
			m_City = m_CitySystem.City
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, outJobHandle, m_Writers));
		m_Writers = base.Dependency;
		TriggerJob jobData3 = new TriggerJob
		{
			m_Entities = m_CollectedFeeGroup.ToEntityArray(Allocator.TempJob),
			m_FeeDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_CollectedCityServiceFeeData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ActionQueue = m_TriggerSystem.CreateActionBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData3, base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (context.purpose == Colossal.Serialization.Entities.Purpose.NewGame)
		{
			CacheFees(reset: true);
		}
		else
		{
			CacheFees();
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
		m_Writers.Complete();
		m_FeeQueue.Clear();
	}
```

- `public static SetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single value) : System.Void`  

```csharp
public static void SetFee(PlayerResource resource, DynamicBuffer<ServiceFee> fees, float value)
	{
		for (int i = 0; i < fees.Length; i++)
		{
			ServiceFee value2 = fees[i];
			if (value2.m_Resource == resource)
			{
				value2.m_Fee = value;
				fees[i] = value2;
				return;
			}
		}
		fees.Add(new ServiceFee
		{
			m_Fee = value,
			m_Resource = resource
		});
	}
```

- `public static TryGetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single& fee) : System.Boolean`  

```csharp
public static bool TryGetFee(PlayerResource resource, DynamicBuffer<ServiceFee> fees, out float fee)
	{
		for (int i = 0; i < fees.Length; i++)
		{
			ServiceFee serviceFee = fees[i];
			if (serviceFee.m_Resource == resource)
			{
				fee = serviceFee.m_Fee;
				return true;
			}
		}
		fee = 0f;
		return false;
	}
```


## Nested types

- `Game.Simulation.ServiceFeeSystem+FeeEvent`  
- `Game.Simulation.ServiceFeeSystem+PayFeeJob`  
- `Game.Simulation.ServiceFeeSystem+FeeToCityJob`  
- `Game.Simulation.ServiceFeeSystem+TriggerJob`  
- `Game.Simulation.ServiceFeeSystem+TypeHandle`  

