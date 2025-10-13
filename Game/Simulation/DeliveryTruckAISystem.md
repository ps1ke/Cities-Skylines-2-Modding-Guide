# Game.Simulation.DeliveryTruckAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeliveryTruckAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.DeliveryTruckAISystem+Actions m_Actions;
    private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
    private Game.Simulation.DeliveryTruckAISystem+TypeHandle __TypeHandle;

    public DeliveryTruckAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.DeliveryTruckAISystem+Actions m_Actions`  

```csharp
private Game.Simulation.DeliveryTruckAISystem+Actions m_Actions;
```

- `private Unity.Entities.EntityQuery m_DeliveryTruckQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
```

- `private Game.Simulation.DeliveryTruckAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DeliveryTruckAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DeliveryTruckAISystem()`  

```csharp
[Preserve]
	public DeliveryTruckAISystem()
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_Actions = base.World.GetOrCreateSystemManaged<Actions>();
		m_DeliveryTruckQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Vehicles.DeliveryTruck>(), ComponentType.ReadOnly<CarCurrentLane>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<TripSource>(), ComponentType.Exclude<OutOfControl>());
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
		uint index = m_SimulationSystem.frameIndex % 16;
		m_DeliveryTruckQuery.ResetFilter();
		m_DeliveryTruckQuery.SetSharedComponentFilter(new UpdateFrame(index));
		m_Actions.m_DeliveredQueue = new NativeQueue<DeliveredStack>(Allocator.TempJob);
		m_Actions.m_RemoveGuestVehicleQueue = new NativeQueue<RemoveGuestVehicle>(Allocator.TempJob);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new DeliveryTruckTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathInformationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LayoutElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Car_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_QuantityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Quantity_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_DeliveryTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ReturnLoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ReturnLoad_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_DeliveredQueue = m_Actions.m_DeliveredQueue.AsParallelWriter(),
			m_RemoveGuestVehicleQueue = m_Actions.m_RemoveGuestVehicleQueue.AsParallelWriter()
		}, m_DeliveryTruckQuery, base.Dependency);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_Actions.m_Dependency = jobHandle;
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.DeliveryTruckAISystem+DeliveredStack`  
- `Game.Simulation.DeliveryTruckAISystem+RemoveGuestVehicle`  
- `Game.Simulation.DeliveryTruckAISystem+Actions`  
- `Game.Simulation.DeliveryTruckAISystem+DeliverJob`  
- `Game.Simulation.DeliveryTruckAISystem+DeliveryTruckTickJob`  
- `Game.Simulation.DeliveryTruckAISystem+TypeHandle`  

