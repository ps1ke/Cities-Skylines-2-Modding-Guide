# Game.UI.InGame.LineVisualizerSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LineVisualizerSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private UnityEngine.Color <color>k__BackingField;
    private System.Int32 <stopCapacity>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> <stops>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> <vehicles>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> <segments>k__BackingField;
    private Unity.Collections.NativeArray<System.Boolean> m_BoolResult;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityResult;
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> m_SegmentsResult;
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> m_StopsResult;
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> m_VehiclesResult;
    private Unity.Collections.NativeArray<UnityEngine.Color32> m_ColorResult;
    private Unity.Collections.NativeArray<System.Int32> m_StopCapacityResult;
    private Game.UI.InGame.LineVisualizerSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    private UnityEngine.Color color { private get; private set; }
    private System.Int32 stopCapacity { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> stops { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> vehicles { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> segments { private get; private set; }

    public LineVisualizerSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private UnityEngine.Color <color>k__BackingField`  

```csharp
private UnityEngine.Color <color>k__BackingField;
```

- `private System.Int32 <stopCapacity>k__BackingField`  

```csharp
private System.Int32 <stopCapacity>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> <stops>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> <stops>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> <vehicles>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> <vehicles>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> <segments>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> <segments>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_BoolResult`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_BoolResult;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityResult`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> m_SegmentsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> m_SegmentsResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> m_StopsResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> m_StopsResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> m_VehiclesResult`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> m_VehiclesResult;
```

- `private Unity.Collections.NativeArray<UnityEngine.Color32> m_ColorResult`  

```csharp
private Unity.Collections.NativeArray<UnityEngine.Color32> m_ColorResult;
```

- `private Unity.Collections.NativeArray<System.Int32> m_StopCapacityResult`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_StopCapacityResult;
```

- `private Game.UI.InGame.LineVisualizerSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LineVisualizerSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `private UnityEngine.Color color { private get; private set }`  

```csharp
private UnityEngine.Color color { private get; private set; }
```

- `private System.Int32 stopCapacity { private get; private set }`  

```csharp
private System.Int32 stopCapacity { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> stops { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineStop> stops { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> vehicles { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineVehicle> vehicles { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> segments { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.LineVisualizerSection+LineSegment> segments { private get; private set; }
```


## Constructors

- `public LineVisualizerSection()`  

```csharp
[Preserve]
	public LineVisualizerSection()
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
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		stops = new NativeList<LineStop>(Allocator.Persistent);
		vehicles = new NativeList<LineVehicle>(Allocator.Persistent);
		segments = new NativeList<LineSegment>(Allocator.Persistent);
		m_BoolResult = new NativeArray<bool>(3, Allocator.Persistent);
		m_EntityResult = new NativeArray<Entity>(1, Allocator.Persistent);
		m_ColorResult = new NativeArray<Color32>(1, Allocator.Persistent);
		m_StopCapacityResult = new NativeArray<int>(1, Allocator.Persistent);
		m_SegmentsResult = new NativeList<LineSegment>(Allocator.Persistent);
		m_StopsResult = new NativeList<LineStop>(Allocator.Persistent);
		m_VehiclesResult = new NativeList<LineVehicle>(Allocator.Persistent);
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
		stops.Dispose();
		vehicles.Dispose();
		segments.Dispose();
		m_BoolResult.Dispose();
		m_EntityResult.Dispose();
		m_ColorResult.Dispose();
		m_StopCapacityResult.Dispose();
		m_SegmentsResult.Dispose();
		m_StopsResult.Dispose();
		m_VehiclesResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		color = m_ColorResult[0];
		stopCapacity = m_StopCapacityResult[0];
		m_InfoUISystem.tooltipTags.Add(m_BoolResult[2] ? TooltipTags.CargoRoute : ((!base.EntityManager.HasComponent<Game.Routes.TransportStop>(selectedEntity)) ? TooltipTags.TransportLine : TooltipTags.TransportStop));
		for (int i = 0; i < m_SegmentsResult.Length; i++)
		{
			segments.Add(m_SegmentsResult[i]);
		}
		for (int j = 0; j < m_VehiclesResult.Length; j++)
		{
			vehicles.Add(m_VehiclesResult[j]);
		}
		for (int k = 0; k < m_StopsResult.Length; k++)
		{
			stops.Add(m_StopsResult[k]);
		}
		m_Dirty = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		IJobExtensions.Schedule(new VisibilityJob
		{
			m_SelectedEntity = selectedEntity,
			m_SelectedRouteEntity = m_InfoUISystem.selectedRoute,
			m_Routes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Route_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportLines = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportLine_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportStops = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiStands = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TaxiStand_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Vehicles = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransports = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentRoutes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteWaypointBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteSegmentBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
			m_RouteVehicleBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedRouteBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjectBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgradeBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_BoolResult = m_BoolResult,
			m_EntityResult = m_EntityResult
		}, base.Dependency).Complete();
		base.visible = m_BoolResult[0];
		if (base.visible)
		{
			if (m_BoolResult[1])
			{
				m_InfoUISystem.selectedRoute = m_EntityResult[0];
			}
			IJobExtensions.Schedule(new UpdateJob
			{
				m_RightHandTraffic = !m_CityConfigurationSystem.leftHandTraffic,
				m_RouteEntity = m_InfoUISystem.selectedRoute,
				m_RenderingFrameIndex = m_RenderingSystem.frameIndex,
				m_RenderingFrameTime = m_RenderingSystem.frameTime,
				m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
				m_UpdateFrames = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
				m_Colors = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Color_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathInformation = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Connected = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WaitingPassengers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_WaitingPassengers_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Positions = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteLanes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentRoutes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathOwners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Owners = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Waypoints = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Trains = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Curves = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLanes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarCurrentLanes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrainCurrentLanes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_WatercraftCurrentLanes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AircraftCurrentLanes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Pets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Pet_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrainDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrainData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PublicTransportVehicleDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PublicTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CargoTransportVehicleDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CullingInfos = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportStops = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EconomyResourcesBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteWaypointBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteSegmentBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteVehicleBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
				m_LayoutElementBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CarNavigationLaneBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_CarNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_TrainNavigationLaneBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_TrainNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_WatercraftNavigationLaneBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_AircraftNavigationLaneBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_AircraftNavigationLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_PathElementBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubLaneBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_PassengerBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferLookup, ref base.CheckedStateRef),
				m_TransformFrames = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_TransformFrame_RO_BufferLookup, ref base.CheckedStateRef),
				m_StorageLimitDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_SegmentsResult = m_SegmentsResult,
				m_StopsResult = m_StopsResult,
				m_VehiclesResult = m_VehiclesResult,
				m_ColorResult = m_ColorResult,
				m_StopCapacityResult = m_StopCapacityResult,
				m_BoolResult = m_BoolResult
			}, base.Dependency).Complete();
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("color");
		writer.Write(color);
		writer.PropertyName("stops");
		writer.ArrayBegin(stops.Length);
		for (int i = 0; i < stops.Length; i++)
		{
			stops[i].Bind(writer, m_NameSystem);
		}
		writer.ArrayEnd();
		writer.PropertyName("vehicles");
		writer.ArrayBegin(vehicles.Length);
		for (int j = 0; j < vehicles.Length; j++)
		{
			vehicles[j].Bind(writer, m_NameSystem);
		}
		writer.ArrayEnd();
		writer.PropertyName("segments");
		writer.ArrayBegin(segments.Length);
		for (int k = 0; k < segments.Length; k++)
		{
			writer.Write(segments[k]);
		}
		writer.ArrayEnd();
		writer.PropertyName("stopCapacity");
		writer.Write(stopCapacity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		color = default(UnityEngine.Color);
		stopCapacity = 0;
		stops.Clear();
		vehicles.Clear();
		segments.Clear();
		m_SegmentsResult.Clear();
		m_StopsResult.Clear();
		m_VehiclesResult.Clear();
	}
```


## Nested types

- `Game.UI.InGame.LineVisualizerSection+LineStop`  
- `Game.UI.InGame.LineVisualizerSection+LineVehicle`  
- `Game.UI.InGame.LineVisualizerSection+LineSegment`  
- `Game.UI.InGame.LineVisualizerSection+Result`  
- `Game.UI.InGame.LineVisualizerSection+VisibilityJob`  
- `Game.UI.InGame.LineVisualizerSection+UpdateJob`  
- `Game.UI.InGame.LineVisualizerSection+TypeHandle`  

