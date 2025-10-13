# Game.Simulation.PowerPlantAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PowerPlantAISystem : Game.GameSystemBase
{
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Unity.Entities.EntityQuery m_PowerPlantQuery;
    private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_833752410_0;
    public static const System.Int32 MAX_WATERPOWERED_SIZE;

    public PowerPlantAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float2 GetGroundWaterProduction(Game.Prefabs.GroundWaterPoweredData groundWaterData, Unity.Mathematics.float3 position, System.Single efficiency, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    public static System.Single GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, Game.Prefabs.WaterPoweredData waterData);
    public static Unity.Mathematics.float2 GetWindProduction(Game.Prefabs.WindPoweredData windData, Game.Simulation.Wind wind, System.Single efficiency);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Unity.Entities.EntityQuery m_PowerPlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PowerPlantQuery;
```

- `private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_833752410_0`  

```csharp
private Unity.Entities.EntityQuery __query_833752410_0;
```

- `public static const System.Int32 MAX_WATERPOWERED_SIZE`  

```csharp
public static const System.Int32 MAX_WATERPOWERED_SIZE;
```


## Constructors

- `public PowerPlantAISystem()`  

```csharp
[Preserve]
	public PowerPlantAISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ElectricityParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_833752410_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public static GetGroundWaterProduction(Game.Prefabs.GroundWaterPoweredData groundWaterData, Unity.Mathematics.float3 position, System.Single efficiency, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap) : Unity.Mathematics.float2`  

```csharp
public static float2 GetGroundWaterProduction(GroundWaterPoweredData groundWaterData, float3 position, float efficiency, NativeArray<GroundWater> groundWaterMap)
	{
		float num = (float)GroundWaterSystem.GetGroundWater(position, groundWaterMap).m_Amount / (float)groundWaterData.m_MaximumGroundWater;
		float num2 = efficiency * (float)groundWaterData.m_Production;
		return new float2(math.clamp(num2 * num, 0f, num2), num2);
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

- `public static GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, Game.Prefabs.WaterPoweredData waterData) : System.Single`  

```csharp
public static float GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, WaterPoweredData waterData)
	{
		return math.min(waterPowered.m_Length * waterPowered.m_Height, 1000000f) * waterData.m_CapacityFactor;
	}
```

- `public static GetWindProduction(Game.Prefabs.WindPoweredData windData, Game.Simulation.Wind wind, System.Single efficiency) : Unity.Mathematics.float2`  

```csharp
public static float2 GetWindProduction(WindPoweredData windData, Wind wind, float efficiency)
	{
		float num = efficiency * (float)windData.m_Production;
		float x = math.lengthsq(wind.m_Wind) / (windData.m_MaximumWind * windData.m_MaximumWind);
		return new float2(num * math.saturate(math.pow(x, 1.5f)), num);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_ClimateSystem = base.World.GetExistingSystemManaged<ClimateSystem>();
		m_PowerPlantQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityProducer>(), ComponentType.ReadOnly<ElectricityBuildingConnection>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_PowerPlantQuery);
		RequireForUpdate<ElectricityParameterData>();
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
		ElectricityParameterData singleton = __query_833752410_0.GetSingleton<ElectricityParameterData>();
		PlanetarySystem.LightData sunLight = m_PlanetarySystem.SunLight;
		float num = 0f;
		if (sunLight.isValid)
		{
			num = math.max(0f, 0f - sunLight.transform.forward.y) * sunLight.additionalData.intensity / 110000f;
		}
		num *= math.lerp(1f, 1f - singleton.m_CloudinessSolarPenalty, m_ClimateSystem.cloudiness.value);
		JobHandle dependencies;
		JobHandle deps;
		JobHandle dependencies2;
		PowerPlantTickJob jobData = new PowerPlantTickJob
		{
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GarbageFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageFacility_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResourceConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPoweredType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPowered_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ElectricityProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityProducer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ServiceUsageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ServiceUsage_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PointOfInterestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_PointOfInterest_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PowerPlantDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PowerPlantData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbagePoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbagePoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WindPoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WindPoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterPoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SolarPoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SolarPoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GroundWaterPoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GroundWaterPoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ResourceConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Curves = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Compositions = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUsages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUsage_RW_ComponentLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_WindMap = m_WindSystem.GetMap(readOnly: true, out dependencies),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetVelocitiesSurfaceData(out deps),
			m_GroundWaterMap = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies2),
			m_SunLight = num
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_PowerPlantQuery, JobUtils.CombineDependencies(base.Dependency, dependencies, deps, dependencies2));
		m_WindSystem.AddReader(base.Dependency);
		m_TerrainSystem.AddCPUHeightReader(base.Dependency);
		m_WaterSystem.AddVelocitySurfaceReader(base.Dependency);
		m_GroundWaterSystem.AddReader(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.PowerPlantAISystem+PowerPlantTickJob`  
- `Game.Simulation.PowerPlantAISystem+TypeHandle`  

