# Game.Simulation.WeatherPhenomenonSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WeatherPhenomenonSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_PhenomenonQuery;
    private Unity.Entities.EntityArchetype m_FaceWeatherArchetype;
    private Unity.Entities.EntityArchetype m_ImpactArchetype;
    private Unity.Entities.EntityArchetype m_EndangerArchetype;
    private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
    private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
    private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle;

    public WeatherPhenomenonSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
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

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem`  

```csharp
private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_PhenomenonQuery`  

```csharp
private Unity.Entities.EntityQuery m_PhenomenonQuery;
```

- `private Unity.Entities.EntityArchetype m_FaceWeatherArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_FaceWeatherArchetype;
```

- `private Unity.Entities.EntityArchetype m_ImpactArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ImpactArchetype;
```

- `private Unity.Entities.EntityArchetype m_EndangerArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EndangerArchetype;
```

- `private Unity.Entities.EntityArchetype m_EventIgniteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
```

- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
```

- `private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WeatherPhenomenonSystem()`  

```csharp
[Preserve]
	public WeatherPhenomenonSystem()
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
		return 0;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ClimateRenderSystem = base.World.GetExistingSystemManaged<ClimateRenderSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_PhenomenonQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Events.WeatherPhenomenon>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_FaceWeatherArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<FaceWeather>());
		m_ImpactArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Impact>());
		m_EndangerArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Endanger>());
		m_EventIgniteArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Ignite>());
		m_EDWSBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.EarlyDisasterWarningSystem>());
		RequireForUpdate(m_PhenomenonQuery);
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
		JobHandle dependencies;
		JobHandle deps;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		WeatherPhenomenonJob jobData = new WeatherPhenomenonJob
		{
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_FaceWeatherArchetype = m_FaceWeatherArchetype,
			m_ImpactArchetype = m_ImpactArchetype,
			m_EndangerArchetype = m_EndangerArchetype,
			m_EventIgniteArchetype = m_EventIgniteArchetype,
			m_WindData = m_WindSystem.GetData(readOnly: true, out dependencies),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_City = m_CitySystem.City,
			m_StaticObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies3),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_LightningStrikes = m_ClimateRenderSystem.GetLightningStrikeQueue(out dependencies4).AsParallelWriter(),
			m_EarlyDisasterWarningSystems = m_EDWSBuildingQuery.ToEntityArray(Allocator.TempJob),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DurationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Duration_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WeatherPhenomenonType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_WeatherPhenomenon_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HotspotFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Events_HotspotFrame_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_DangerLevelType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_DangerLevel_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmergencyShelterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_EmergencyShelter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceholderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Placeholder_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InvolvedInAccidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InvolvedInAccident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FacingWeatherData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_FacingWeather_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InDangerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InDanger_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WeatherPhenomenonData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WeatherPhenomenonData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficAccidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrafficAccidentData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_FireData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDestructibleObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DestructibleObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef)
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_PhenomenonQuery, JobUtils.CombineDependencies(base.Dependency, dependencies, deps, dependencies2, dependencies3, dependencies4));
		jobData.m_EarlyDisasterWarningSystems.Dispose(jobHandle);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_WindSystem.AddReader(jobHandle);
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		m_ClimateRenderSystem.AddLightningStrikeWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.WeatherPhenomenonSystem+WeatherPhenomenonJob`  
- `Game.Simulation.WeatherPhenomenonSystem+TypeHandle`  

