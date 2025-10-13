# Game.Simulation.AdjustElectricityConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AdjustElectricityConsumptionSystem : Game.GameSystemBase
{
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Unity.Entities.EntityQuery m_ConsumerQuery;
    private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_653552652_0;
    private Unity.Entities.EntityQuery __query_653552652_1;
    private Unity.Entities.EntityQuery __query_653552652_2;
    private static const System.Int32 kFullUpdatesPerDay;

    public AdjustElectricityConsumptionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
    public static System.Single GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
    public System.Single GetTemperatureMultiplier(System.Single temperature);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Unity.Entities.EntityQuery m_ConsumerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerQuery;
```

- `private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_653552652_0`  

```csharp
private Unity.Entities.EntityQuery __query_653552652_0;
```

- `private Unity.Entities.EntityQuery __query_653552652_1`  

```csharp
private Unity.Entities.EntityQuery __query_653552652_1;
```

- `private Unity.Entities.EntityQuery __query_653552652_2`  

```csharp
private Unity.Entities.EntityQuery __query_653552652_2;
```

- `private static const System.Int32 kFullUpdatesPerDay`  

```csharp
private static const System.Int32 kFullUpdatesPerDay;
```


## Constructors

- `public AdjustElectricityConsumptionSystem()`  

```csharp
[Preserve]
	public AdjustElectricityConsumptionSystem()
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
		__query_653552652_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<BuildingEfficiencyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_653552652_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<ElectricityParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_653552652_2 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public static GetFeeConsumptionMultiplier(System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters) : System.Single`  

```csharp
public static float GetFeeConsumptionMultiplier(float relativeFee, in ServiceFeeParameterData feeParameters)
	{
		return feeParameters.m_ElectricityFeeConsumptionMultiplier.Evaluate(relativeFee);
	}
```

- `public static GetFeeEfficiencyFactor(System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters) : System.Single`  

```csharp
public static float GetFeeEfficiencyFactor(float relativeFee, in BuildingEfficiencyParameterData efficiencyParameters)
	{
		return efficiencyParameters.m_ElectricityFeeFactor.Evaluate(relativeFee);
	}
```

- `public GetTemperatureMultiplier(System.Single temperature) : System.Single`  

```csharp
public float GetTemperatureMultiplier(float temperature)
	{
		if (!__query_653552652_2.TryGetSingleton<ElectricityParameterData>(out var value))
		{
			return 1f;
		}
		return value.m_TemperatureConsumptionMultiplier.Evaluate(temperature);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 0;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		Assert.IsTrue(GetUpdateInterval(SystemUpdatePhase.GameSimulation) >= 128);
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_ConsumerQuery = GetEntityQuery(ComponentType.ReadWrite<ElectricityConsumer>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_ConsumerQuery);
		RequireForUpdate<ServiceFeeParameterData>();
		RequireForUpdate<BuildingEfficiencyParameterData>();
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
		NativeQueue<Entity> updatedEdges = new NativeQueue<Entity>(Allocator.TempJob);
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, 128, 16);
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(new AdjustElectricityConsumptionJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CityServiceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_City_CityServiceUpkeep_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StoragePropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_StorageProperty_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceConsumption = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Fees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedEdges = updatedEdges.AsParallelWriter(),
			m_FeeParameters = __query_653552652_0.GetSingleton<ServiceFeeParameterData>(),
			m_EfficiencyParameters = __query_653552652_1.GetSingleton<BuildingEfficiencyParameterData>(),
			m_RandomSeed = RandomSeed.Next(),
			m_City = m_CitySystem.City,
			m_TemperatureMultiplier = GetTemperatureMultiplier(m_ClimateSystem.temperature),
			m_UpdateFrameIndex = updateFrame
		}, m_ConsumerQuery, base.Dependency);
		UpdateEdgesJob jobData = new UpdateEdgesJob
		{
			m_NodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Consumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedBuildings = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_ConnectedBuilding_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_UpdatedEdges = updatedEdges,
			m_SinkNode = m_ElectricityFlowSystem.sinkNode
		};
		base.Dependency = IJobExtensions.Schedule(jobData, dependsOn);
		updatedEdges.Dispose(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.AdjustElectricityConsumptionSystem+AdjustElectricityConsumptionJob`  
- `Game.Simulation.AdjustElectricityConsumptionSystem+UpdateEdgesJob`  
- `Game.Simulation.AdjustElectricityConsumptionSystem+TypeHandle`  

