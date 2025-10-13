# Game.Simulation.AccidentSiteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AccidentSiteSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_AccidentQuery;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityArchetype m_PoliceRequestArchetype;
    private Unity.Entities.EntityArchetype m_EventImpactArchetype;
    private Game.Simulation.AccidentSiteSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public AccidentSiteSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_AccidentQuery`  

```csharp
private Unity.Entities.EntityQuery m_AccidentQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_PoliceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PoliceRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_EventImpactArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventImpactArchetype;
```

- `private Game.Simulation.AccidentSiteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AccidentSiteSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public AccidentSiteSystem()`  

```csharp
[Preserve]
	public AccidentSiteSystem()
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
		return 64;
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
		m_AccidentQuery = GetEntityQuery(ComponentType.ReadWrite<AccidentSite>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_PoliceRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<PoliceEmergencyRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_EventImpactArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Impact>());
		RequireForUpdate(m_AccidentQuery);
		Assert.IsTrue(condition: true);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new AccidentSiteJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AccidentSiteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_AccidentSite_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InvolvedInAccidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InvolvedInAccident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CriminalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Criminal_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PoliceEmergencyRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_PoliceEmergencyRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTrafficAccidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrafficAccidentData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCrimeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CrimeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_PoliceRequestArchetype = m_PoliceRequestArchetype,
			m_EventImpactArchetype = m_EventImpactArchetype,
			m_PoliceConfigurationData = m_ConfigQuery.GetSingleton<PoliceConfigurationData>(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		}, m_AccidentQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.AccidentSiteSystem+AccidentSiteJob`  
- `Game.Simulation.AccidentSiteSystem+TypeHandle`  

