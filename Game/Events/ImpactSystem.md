# Game.Events.ImpactSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ImpactSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_ImpactQuery;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes;
    private Game.Events.ImpactSystem+TypeHandle __TypeHandle;

    public ImpactSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_ImpactQuery`  

```csharp
private Unity.Entities.EntityQuery m_ImpactQuery;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingPersonalCarAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingServiceCarAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes;
```

- `private Game.Events.ImpactSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.ImpactSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ImpactSystem()`  

```csharp
[Preserve]
	public ImpactSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ImpactQuery = GetEntityQuery(ComponentType.ReadOnly<Impact>(), ComponentType.ReadOnly<Game.Common.Event>());
		m_ParkedToMovingCarRemoveTypes = new ComponentTypeSet(ComponentType.ReadWrite<ParkedCar>(), ComponentType.ReadWrite<Stopped>());
		m_ParkedToMovingPersonalCarAddTypes = new ComponentTypeSet(new ComponentType[12]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_ParkedToMovingTaxiAddTypes = new ComponentTypeSet(new ComponentType[13]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<ServiceDispatch>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_ParkedToMovingServiceCarAddTypes = new ComponentTypeSet(new ComponentType[14]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<PathInformation>(),
			ComponentType.ReadWrite<ServiceDispatch>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_ParkedToMovingTrailerAddTypes = new ComponentTypeSet(new ComponentType[6]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarTrailerLane>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		RequireForUpdate(m_ImpactQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_ImpactQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new AddImpactJob
		{
			m_ImpactType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Impact_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StoppedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarTrailerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarTrailer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarTrailerLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarTrailerLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PersonalCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarageLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ControllerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Controller_RW_ComponentLookup, ref base.CheckedStateRef),
			m_InvolvedInAccidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InvolvedInAccident_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_Chunks = chunks,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_ParkedToMovingCarRemoveTypes = m_ParkedToMovingCarRemoveTypes,
			m_ParkedToMovingPersonalCarAddTypes = m_ParkedToMovingPersonalCarAddTypes,
			m_ParkedToMovingTaxiAddTypes = m_ParkedToMovingTaxiAddTypes,
			m_ParkedToMovingServiceCarAddTypes = m_ParkedToMovingServiceCarAddTypes,
			m_ParkedToMovingTrailerAddTypes = m_ParkedToMovingTrailerAddTypes,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Events.ImpactSystem+AddImpactJob`  
- `Game.Events.ImpactSystem+TypeHandle`  

