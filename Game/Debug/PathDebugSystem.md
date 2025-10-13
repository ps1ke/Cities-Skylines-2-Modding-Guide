# Game.Debug.PathDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_PathGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption;
    private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption;
    private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption;
    private Game.Debug.BaseDebugSystem+Option m_ResidentOption;
    private Game.Debug.BaseDebugSystem+Option m_CitizenOption;
    private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
    private Game.Debug.BaseDebugSystem+Option m_RouteOption;
    private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption;
    private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption;
    private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle;

    public PathDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle DrawPathGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PathGroup`  

```csharp
private Unity.Entities.EntityQuery m_PathGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ResidentOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ResidentOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CitizenOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CitizenOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CompanyOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RouteOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption;
```

- `private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PathDebugSystem()`  

```csharp
[Preserve]
	public PathDebugSystem()
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

- `private DrawPathGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle DrawPathGizmos(EntityQuery group, JobHandle inputDeps)
	{
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new PathGizmoJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PersonalCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DeliveryTruckType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_JobSeekerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Agents_JobSeeker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SchoolSeekerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_SchoolSeeker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompanyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RouteSegmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GoodsDeliveryRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_GoodsDeliveryRequest_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceRequestType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceRequest_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PersonalCarOption = m_PersonalCarOption.enabled,
			m_DeliveryTruckOption = m_DeliveryTruckOption.enabled,
			m_ServiceVehicleOption = m_ServiceVehicleOption.enabled,
			m_ResidentOption = m_ResidentOption.enabled,
			m_CitizenOption = m_CitizenOption.enabled,
			m_CompanyOption = m_CompanyOption.enabled,
			m_RouteOption = m_RouteOption.enabled,
			m_DeliveryRequestOption = m_DeliveryRequestOption.enabled,
			m_ServiceRequestOption = m_ServiceRequestOption.enabled,
			m_TimeOffset = UnityEngine.Time.realtimeSinceStartup,
			m_Selected = m_ToolSystem.selected,
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies)
		}, group, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PathGroup = GetEntityQuery(ComponentType.ReadOnly<PathElement>(), ComponentType.Exclude<Deleted>());
		m_PersonalCarOption = AddOption("Personal cars", defaultEnabled: true);
		m_DeliveryTruckOption = AddOption("Delivery trucks", defaultEnabled: true);
		m_ServiceVehicleOption = AddOption("Service vehicles", defaultEnabled: true);
		m_ResidentOption = AddOption("Citizens (instance)", defaultEnabled: true);
		m_CitizenOption = AddOption("Citizens (agent)", defaultEnabled: false);
		m_CompanyOption = AddOption("Companies", defaultEnabled: false);
		m_RouteOption = AddOption("Transport routes", defaultEnabled: false);
		m_DeliveryRequestOption = AddOption("Delivery requests", defaultEnabled: false);
		m_ServiceRequestOption = AddOption("Service requests", defaultEnabled: false);
		base.Enabled = false;
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
		if (!m_PathGroup.IsEmptyIgnoreFilter)
		{
			base.Dependency = DrawPathGizmos(m_PathGroup, base.Dependency);
		}
	}
```


## Nested types

- `Game.Debug.PathDebugSystem+PathGizmoJob`  
- `Game.Debug.PathDebugSystem+TypeHandle`  

