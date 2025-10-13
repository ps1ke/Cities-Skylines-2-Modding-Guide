# Game.Simulation.CrimeAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CrimeAccumulationSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Unity.Entities.EntityQuery m_PoliceConfigurationQuery;
    private Unity.Entities.EntityArchetype m_PatrolRequestArchetype;
    private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kUpdateInterval;

    public CrimeAccumulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceConfigurationQuery;
```

- `private Unity.Entities.EntityArchetype m_PatrolRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PatrolRequestArchetype;
```

- `private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CrimeAccumulationSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kUpdateInterval`  

```csharp
public static readonly System.Int32 kUpdateInterval;
```


## Constructors

- `public CrimeAccumulationSystem()`  

```csharp
[Preserve]
	public CrimeAccumulationSystem()
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
		return kUpdateInterval;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CrimeProducerQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<CrimeProducer>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_PoliceConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_PatrolRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<PolicePatrolRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireForUpdate(m_CrimeProducerQuery);
		Assert.IsTrue((long)(kUpdateInterval * 16) >= 512L);
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
		PoliceConfigurationData singleton = m_PoliceConfigurationQuery.GetSingleton<PoliceConfigurationData>();
		if (!base.EntityManager.HasEnabledComponent<Locked>(singleton.m_PoliceServicePrefab))
		{
			uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
			m_CrimeProducerQuery.ResetFilter();
			m_CrimeProducerQuery.SetSharedComponentFilter(new UpdateFrame(updateFrameWithInterval));
			JobHandle dependencies;
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new CrimeAccumulationJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CrimeProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CrimeProducer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PolicePatrolRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_PolicePatrolRequest_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CrimeAccumulationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CrimeAccumulationData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_ServiceCoverages = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_City = m_CitySystem.City,
				m_PatrolRequestArchetype = m_PatrolRequestArchetype,
				m_PoliceConfigurationData = singleton,
				m_LocalEffectData = m_LocalEffectSystem.GetReadData(out dependencies),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_RandomSeed = RandomSeed.Next()
			}, m_CrimeProducerQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
			m_LocalEffectSystem.AddLocalEffectReader(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Simulation.CrimeAccumulationSystem+CrimeAccumulationJob`  
- `Game.Simulation.CrimeAccumulationSystem+TypeHandle`  

