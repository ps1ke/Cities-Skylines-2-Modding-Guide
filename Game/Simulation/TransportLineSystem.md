# Game.Simulation.TransportLineSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportLineSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_LineQuery;
    private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
    private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed;
    private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 UPDATE_INTERVAL;

    public TransportLineSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 CalculateVehicleCount(System.Single vehicleInterval, System.Single lineDuration);
    public static System.Single CalculateVehicleInterval(System.Single lineDuration, System.Int32 vehicleCount);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void GetMaxTransportSpeed(System.Single& maxPassengerTransportSpeed, System.Single& maxCargoTransportSpeed);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LineQuery`  

```csharp
private Unity.Entities.EntityQuery m_LineQuery;
```

- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
```

- `private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed;
```

- `private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps`  

```csharp
private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public TransportLineSystem()`  

```csharp
[Preserve]
	public TransportLineSystem()
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

- `public static CalculateVehicleCount(System.Single vehicleInterval, System.Single lineDuration) : System.Int32`  

```csharp
public static int CalculateVehicleCount(float vehicleInterval, float lineDuration)
	{
		return math.max(1, (int)math.round(lineDuration / math.max(1f, vehicleInterval)));
	}
```

- `public static CalculateVehicleInterval(System.Single lineDuration, System.Int32 vehicleCount) : System.Single`  

```csharp
public static float CalculateVehicleInterval(float lineDuration, int vehicleCount)
	{
		return lineDuration / (float)math.max(1, vehicleCount);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetMaxTransportSpeed(System.Single& maxPassengerTransportSpeed, System.Single& maxCargoTransportSpeed) : System.Void`  

```csharp
public void GetMaxTransportSpeed(out float maxPassengerTransportSpeed, out float maxCargoTransportSpeed)
	{
		m_MaxTransportSpeedDeps.Complete();
		maxPassengerTransportSpeed = m_MaxTransportSpeed[0];
		maxCargoTransportSpeed = m_MaxTransportSpeed[1];
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 256;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_LineQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.ReadWrite<TransportLine>(), ComponentType.ReadOnly<RouteWaypoint>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_VehicleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<TransportVehicleRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_MaxTransportSpeed = new NativeArray<float>(2, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_MaxTransportSpeed.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_MaxTransportSpeed[0] = 0f;
		m_MaxTransportSpeed[1] = 0f;
		if (!m_LineQuery.IsEmptyIgnoreFilter)
		{
			NativeQueue<VehicleAction> actionQueue = new NativeQueue<VehicleAction>(Allocator.TempJob);
			float normalizedTime = m_TimeSystem.normalizedTime;
			bool isNight = normalizedTime < 0.25f || normalizedTime >= 11f / 12f;
			TransportLineTickJob jobData = new TransportLineTickJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_RouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Route_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_VehicleModelType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_VehicleModel_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RouteWaypointType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_RouteSegmentType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_RouteModifierType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteModifier_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TransportLineType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TransportLine_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RouteVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteVehicle_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_DispatchedRequestType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_DispatchedRequest_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_VehicleTimingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_VehicleTiming_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DispatchedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Dispatched_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CargoTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CargoTransport_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OdometerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Odometer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportLineDataData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteInfo_RW_ComponentLookup, ref base.CheckedStateRef),
				m_VehicleRequestArchetype = m_VehicleRequestArchetype,
				m_IsNight = isNight,
				m_MaxTransportSpeed = m_MaxTransportSpeed,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_ActionQueue = actionQueue.AsParallelWriter(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
			};
			VehicleActionJob jobData2 = new VehicleActionJob
			{
				m_CargoTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CargoTransport_RW_ComponentLookup, ref base.CheckedStateRef),
				m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ActionQueue = actionQueue
			};
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_LineQuery, base.Dependency);
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
			actionQueue.Dispose(jobHandle2);
			m_MaxTransportSpeedDeps = jobHandle;
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
			base.Dependency = jobHandle2;
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
		m_MaxTransportSpeed[0] = 277.77777f;
		m_MaxTransportSpeed[1] = 277.77777f;
	}
```


## Nested types

- `Game.Simulation.TransportLineSystem+SortedVehicle`  
- `Game.Simulation.TransportLineSystem+VehicleAction`  
- `Game.Simulation.TransportLineSystem+VehicleActionType`  
- `Game.Simulation.TransportLineSystem+TransportLineTickJob`  
- `Game.Simulation.TransportLineSystem+VehicleActionJob`  
- `Game.Simulation.TransportLineSystem+TypeHandle`  

