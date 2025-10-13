# Game.Simulation.ProcessingCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProcessingCompanySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Collections.NativeArray<System.Int64> m_ProducedResources;
    private Unity.Jobs.JobHandle m_ProducedResourcesDeps;
    private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1038562630_0;
    public static const System.Int32 kMaxCommercialOutputResource;
    public static const System.Single kMaximumTransportUnitCost;

    public ProcessingCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddProducedResourcesReader(Unity.Jobs.JobHandle handle);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int64> GetProducedResourcesArray(Unity.Jobs.JobHandle& dependencies);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

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

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem`  

```csharp
private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Collections.NativeArray<System.Int64> m_ProducedResources`  

```csharp
private Unity.Collections.NativeArray<System.Int64> m_ProducedResources;
```

- `private Unity.Jobs.JobHandle m_ProducedResourcesDeps`  

```csharp
private Unity.Jobs.JobHandle m_ProducedResourcesDeps;
```

- `private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1038562630_0`  

```csharp
private Unity.Entities.EntityQuery __query_1038562630_0;
```

- `public static const System.Int32 kMaxCommercialOutputResource`  

```csharp
public static const System.Int32 kMaxCommercialOutputResource;
```

- `public static const System.Single kMaximumTransportUnitCost`  

```csharp
public static const System.Single kMaximumTransportUnitCost;
```


## Constructors

- `public ProcessingCompanySystem()`  

```csharp
[Preserve]
	public ProcessingCompanySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<EconomyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1038562630_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public AddProducedResourcesReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddProducedResourcesReader(JobHandle handle)
	{
		m_ProducedResourcesDeps = JobHandle.CombineDependencies(m_ProducedResourcesDeps, handle);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetProducedResourcesArray(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public NativeArray<long> GetProducedResourcesArray(out JobHandle dependencies)
	{
		dependencies = base.Dependency;
		return m_ProducedResources;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (EconomyUtils.kCompanyUpdatesPerDay * 16);
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
		m_VehicleCapacitySystem = base.World.GetOrCreateSystemManaged<VehicleCapacitySystem>();
		m_ProductionSpecializationSystem = base.World.GetOrCreateSystemManaged<ProductionSpecializationSystem>();
		m_CitySystem = base.World.GetExistingSystemManaged<CitySystem>();
		m_CompanyGroup = GetEntityQuery(ComponentType.ReadWrite<Game.Companies.ProcessingCompany>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadWrite<Game.Economy.Resources>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<WorkProvider>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Employee>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Game.Companies.ExtractorCompany>());
		RequireForUpdate(m_CompanyGroup);
		RequireForUpdate<EconomyParameterData>();
		m_ProducedResources = new NativeArray<long>(EconomyUtils.ResourceCount, Allocator.Persistent);
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
		m_ProducedResources.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, EconomyUtils.kCompanyUpdatesPerDay, 16);
		JobHandle deps;
		UpdateProcessingJob jobData = new UpdateProcessingJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmployeeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_Employee_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ServiceAvailableType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ServiceAvailable_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_CompanyDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TaxPayerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_TaxPayer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Limits = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Specializations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_SpecializationBonus_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferLookup, ref base.CheckedStateRef),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData(),
			m_ProducedResources = m_ProducedResources,
			m_ProductionQueue = m_ProductionSpecializationSystem.GetQueue(out deps).AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_EconomyParameters = __query_1038562630_0.GetSingleton<EconomyParameterData>(),
			m_RandomSeed = RandomSeed.Next(),
			m_City = m_CitySystem.City,
			m_UpdateFrameIndex = updateFrame
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CompanyGroup, JobHandle.CombineDependencies(m_ProducedResourcesDeps, deps, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
		m_ProductionSpecializationSystem.AddQueueWriter(base.Dependency);
		m_TaxSystem.AddReader(base.Dependency);
		m_ProducedResourcesDeps = default(JobHandle);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (!(context.version < Version.officeFix))
		{
			return;
		}
		ResourcePrefabs prefabs = m_ResourceSystem.GetPrefabs();
		ComponentLookup<ResourceData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef);
		NativeArray<Entity> nativeArray = m_CompanyGroup.ToEntityArray(Allocator.Temp);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(nativeArray[i]).m_Prefab;
			IndustrialProcessData componentData = base.EntityManager.GetComponentData<IndustrialProcessData>(prefab);
			if (!base.EntityManager.HasComponent<ServiceAvailable>(nativeArray[i]) && componentLookup[prefabs[componentData.m_Output.m_Resource]].m_Weight == 0f)
			{
				DynamicBuffer<Game.Economy.Resources> buffer = base.EntityManager.GetBuffer<Game.Economy.Resources>(nativeArray[i]);
				if (EconomyUtils.GetResources(componentData.m_Output.m_Resource, buffer) >= 500)
				{
					EconomyUtils.AddResources(componentData.m_Output.m_Resource, -500, buffer);
				}
			}
		}
		nativeArray.Dispose();
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
		for (int i = 0; i < m_ProducedResources.Length; i++)
		{
			m_ProducedResources[i] = 0L;
		}
	}
```


## Nested types

- `Game.Simulation.ProcessingCompanySystem+UpdateProcessingJob`  
- `Game.Simulation.ProcessingCompanySystem+TypeHandle`  

