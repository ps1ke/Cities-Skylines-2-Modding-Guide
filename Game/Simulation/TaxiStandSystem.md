# Game.Simulation.TaxiStandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TaxiStandSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_StandQuery;
    private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TaxiStandSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 UPDATE_INTERVAL;

    public TaxiStandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StandQuery`  

```csharp
private Unity.Entities.EntityQuery m_StandQuery;
```

- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TaxiStandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TaxiStandSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public TaxiStandSystem()`  

```csharp
[Preserve]
	public TaxiStandSystem()
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
		return 256;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_StandQuery = GetEntityQuery(ComponentType.ReadWrite<TaxiStand>(), ComponentType.ReadOnly<Game.Routes.TransportStop>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_VehicleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<TaxiRequest>(), ComponentType.ReadWrite<RequestGroup>());
		RequireForUpdate(m_StandQuery);
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
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new TaxiStandTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaitingPassengersType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WaitingPassengers_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TaxiStandType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TaxiStand_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_RouteVehicle_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_DispatchedRequestType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Routes_DispatchedRequest_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_TaxiRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_TaxiRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentRouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DispatchedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Dispatched_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_City_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_TaxiRequestArchetype = m_VehicleRequestArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_StandQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.TaxiStandSystem+TaxiStandTickJob`  
- `Game.Simulation.TaxiStandSystem+TypeHandle`  

