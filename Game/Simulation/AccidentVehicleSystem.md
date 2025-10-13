# Game.Simulation.AccidentVehicleSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AccidentVehicleSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype;
    private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
    private Unity.Entities.EntityArchetype m_AddImpactArchetype;
    private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public AccidentVehicleSystem();

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

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype;
```

- `private Unity.Entities.EntityArchetype m_EventIgniteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
```

- `private Unity.Entities.EntityArchetype m_AddImpactArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AddImpactArchetype;
```

- `private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public AccidentVehicleSystem()`  

```csharp
[Preserve]
	public AccidentVehicleSystem()
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
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_VehicleQuery = GetEntityQuery(ComponentType.ReadWrite<InvolvedInAccident>(), ComponentType.ReadOnly<Vehicle>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_AddAccidentSiteArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<AddAccidentSite>());
		m_EventIgniteArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Ignite>());
		m_AddImpactArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Impact>());
		RequireForUpdate(m_VehicleQuery);
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
		PoliceConfigurationData singleton = m_ConfigQuery.GetSingleton<PoliceConfigurationData>();
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new AccidentVehicleJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MovingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DamagedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OnFireType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BlockedLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_BlockedLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PassengerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InvolvedInAccidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_InvolvedInAccident_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AccidentSiteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_AccidentSite_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_FireData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_PoliceConfigurationData = singleton,
			m_AddAccidentSiteArchetype = m_AddAccidentSiteArchetype,
			m_EventIgniteArchetype = m_EventIgniteArchetype,
			m_AddImpactArchetype = m_AddImpactArchetype,
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		}, m_VehicleQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.AccidentVehicleSystem+AccidentVehicleJob`  
- `Game.Simulation.AccidentVehicleSystem+TypeHandle`  

