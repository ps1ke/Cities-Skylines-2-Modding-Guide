# Game.Simulation.PathfindSetupSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathfindSetupSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup;
    private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup;
    private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup;
    private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup;
    private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup;
    private Game.Simulation.FirePathfindSetup m_FirePathfindSetup;
    private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup;
    private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup;
    private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup;
    private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup;
    private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList;
    private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues;
    private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues;
    private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList;
    private Unity.Jobs.JobHandle m_QueueDependencies;
    private Unity.Jobs.JobHandle m_SetupDependencies;
    private System.UInt32 m_QueueSimulationFrameIndex;
    private System.UInt32 m_SetupSimulationFrameIndex;
    private System.Int32 m_PendingRequestCount;

    public System.UInt32 pendingSimulationFrame { get; }
    public System.Int32 pendingRequestCount { get; }

    public PathfindSetupSystem();

    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public System.Void CompleteSetup();
    private System.Void FindTargets(System.Int32 startIndex, System.Int32 endIndex);
    private Unity.Jobs.JobHandle FindTargets(Game.Pathfind.SetupTargetType targetType, Game.Simulation.PathfindSetupSystem+SetupData& setupData);
    public Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> GetQueue(System.Object system, System.Int32 maxDelayFrames, System.Int32 spreadFrames);
    public Unity.Entities.EntityQuery GetSetupQuery(Unity.Entities.EntityQueryDesc[] entityQueryDesc);
    public Unity.Entities.EntityQuery GetSetupQuery(Unity.Entities.ComponentType[] componentTypes);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup`  

```csharp
private Game.Simulation.CommonPathfindSetup m_CommonPathfindSetup;
```

- `private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup`  

```csharp
private Game.Simulation.PostServicePathfindSetup m_PostServicePathfindSetup;
```

- `private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup`  

```csharp
private Game.Simulation.GarbagePathfindSetup m_GarbagePathfindSetup;
```

- `private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup`  

```csharp
private Game.Simulation.TransportPathfindSetup m_TransportPathfindSetup;
```

- `private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup`  

```csharp
private Game.Simulation.PolicePathfindSetup m_PolicePathfindSetup;
```

- `private Game.Simulation.FirePathfindSetup m_FirePathfindSetup`  

```csharp
private Game.Simulation.FirePathfindSetup m_FirePathfindSetup;
```

- `private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup`  

```csharp
private Game.Simulation.HealthcarePathfindSetup m_HealthcarePathfindSetup;
```

- `private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup`  

```csharp
private Game.Simulation.AreaPathfindSetup m_AreaPathfindSetup;
```

- `private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup`  

```csharp
private Game.Simulation.RoadPathfindSetup m_RoadPathfindSetup;
```

- `private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup`  

```csharp
private Game.Simulation.CitizenPathfindSetup m_CitizenPathfindSetup;
```

- `private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup`  

```csharp
private Game.Simulation.ResourcePathfindSetup m_ResourcePathfindSetup;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupList;
```

- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues`  

```csharp
private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_ActiveQueues;
```

- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues`  

```csharp
private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+SetupQueue> m_FreeQueues;
```

- `private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList`  

```csharp
private System.Collections.Generic.List<Game.Simulation.PathfindSetupSystem+ActionListItem> m_ActionList;
```

- `private Unity.Jobs.JobHandle m_QueueDependencies`  

```csharp
private Unity.Jobs.JobHandle m_QueueDependencies;
```

- `private Unity.Jobs.JobHandle m_SetupDependencies`  

```csharp
private Unity.Jobs.JobHandle m_SetupDependencies;
```

- `private System.UInt32 m_QueueSimulationFrameIndex`  

```csharp
private System.UInt32 m_QueueSimulationFrameIndex;
```

- `private System.UInt32 m_SetupSimulationFrameIndex`  

```csharp
private System.UInt32 m_SetupSimulationFrameIndex;
```

- `private System.Int32 m_PendingRequestCount`  

```csharp
private System.Int32 m_PendingRequestCount;
```


## Properties

- `public System.UInt32 pendingSimulationFrame { get }`  

```csharp
public System.UInt32 pendingSimulationFrame { get; }
```

- `public System.Int32 pendingRequestCount { get }`  

```csharp
public System.Int32 pendingRequestCount { get; }
```


## Constructors

- `public PathfindSetupSystem()`  

```csharp
[Preserve]
	public PathfindSetupSystem()
	{
	}
```


## Methods

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddQueueWriter(JobHandle handle)
	{
		m_QueueDependencies = JobHandle.CombineDependencies(m_QueueDependencies, handle);
	}
```

- `public CompleteSetup() : System.Void`  

```csharp
public void CompleteSetup()
	{
		m_SetupSimulationFrameIndex = uint.MaxValue;
		m_PendingRequestCount = 0;
		m_SetupDependencies.Complete();
		m_SetupDependencies = default(JobHandle);
		for (int i = 0; i < m_SetupList.Length; i++)
		{
			SetupListItem setupListItem = m_SetupList[i];
			ActionListItem value = m_ActionList[setupListItem.m_ActionIndex];
			if (setupListItem.m_ActionStart)
			{
				value.m_Action.data.m_StartTargets = setupListItem.m_Buffer;
			}
			else
			{
				value.m_Action.data.m_EndTargets = setupListItem.m_Buffer;
			}
			m_ActionList[setupListItem.m_ActionIndex] = value;
		}
		for (int j = 0; j < m_ActionList.Count; j++)
		{
			ActionListItem actionListItem = m_ActionList[j];
			m_PathfindQueueSystem.Enqueue(actionListItem.m_Action, actionListItem.m_Owner, m_SetupDependencies, actionListItem.m_ResultFrame, actionListItem.m_System);
		}
		m_SetupList.Clear();
		m_ActionList.Clear();
	}
```

- `private FindTargets(System.Int32 startIndex, System.Int32 endIndex) : System.Void`  

```csharp
private JobHandle FindTargets(SetupTargetType targetType, in SetupData setupData)
	{
		switch (targetType)
		{
		case SetupTargetType.CurrentLocation:
			return m_CommonPathfindSetup.SetupCurrentLocation(this, setupData, base.Dependency);
		case SetupTargetType.AccidentLocation:
			return m_CommonPathfindSetup.SetupAccidentLocation(this, setupData, base.Dependency);
		case SetupTargetType.Safety:
			return m_CommonPathfindSetup.SetupSafety(this, setupData, base.Dependency);
		case SetupTargetType.PostVan:
			return m_PostServicePathfindSetup.SetupPostVans(this, setupData, base.Dependency);
		case SetupTargetType.MailTransfer:
			return m_PostServicePathfindSetup.SetupMailTransfer(this, setupData, base.Dependency);
		case SetupTargetType.MailBox:
			return m_PostServicePathfindSetup.SetupMailBoxes(this, setupData, base.Dependency);
		case SetupTargetType.PostVanRequest:
			return m_PostServicePathfindSetup.SetupPostVanRequest(this, setupData, base.Dependency);
		case SetupTargetType.GarbageCollector:
			return m_GarbagePathfindSetup.SetupGarbageCollector(this, setupData, base.Dependency);
		case SetupTargetType.GarbageTransfer:
			return m_GarbagePathfindSetup.SetupGarbageTransfer(this, setupData, base.Dependency);
		case SetupTargetType.GarbageCollectorRequest:
			return m_GarbagePathfindSetup.SetupGarbageCollectorRequest(this, setupData, base.Dependency);
		case SetupTargetType.Taxi:
			return m_TransportPathfindSetup.SetupTaxi(this, setupData, base.Dependency);
		case SetupTargetType.TransportVehicle:
			return m_TransportPathfindSetup.SetupTransportVehicle(this, setupData, base.Dependency);
		case SetupTargetType.RouteWaypoints:
			return m_TransportPathfindSetup.SetupRouteWaypoints(this, setupData, base.Dependency);
		case SetupTargetType.TransportVehicleRequest:
			return m_TransportPathfindSetup.SetupTransportVehicleRequest(this, setupData, base.Dependency);
		case SetupTargetType.TaxiRequest:
			return m_TransportPathfindSetup.SetupTaxiRequest(this, setupData, base.Dependency);
		case SetupTargetType.CrimeProducer:
			return m_PolicePathfindSetup.SetupCrimeProducer(this, setupData, base.Dependency);
		case SetupTargetType.PolicePatrol:
			return m_PolicePathfindSetup.SetupPolicePatrols(this, setupData, base.Dependency);
		case SetupTargetType.PrisonerTransport:
			return m_PolicePathfindSetup.SetupPrisonerTransport(this, setupData, base.Dependency);
		case SetupTargetType.PrisonerTransportRequest:
			return m_PolicePathfindSetup.SetupPrisonerTransportRequest(this, setupData, base.Dependency);
		case SetupTargetType.PoliceRequest:
			return m_PolicePathfindSetup.SetupPoliceRequest(this, setupData, base.Dependency);
		case SetupTargetType.EmergencyShelter:
			return m_FirePathfindSetup.SetupEmergencyShelters(this, setupData, base.Dependency);
		case SetupTargetType.EvacuationTransport:
			return m_FirePathfindSetup.SetupEvacuationTransport(this, setupData, base.Dependency);
		case SetupTargetType.FireEngine:
			return m_FirePathfindSetup.SetupFireEngines(this, setupData, base.Dependency);
		case SetupTargetType.EvacuationRequest:
			return m_FirePathfindSetup.SetupEvacuationRequest(this, setupData, base.Dependency);
		case SetupTargetType.FireRescueRequest:
			return m_FirePathfindSetup.SetupFireRescueRequest(this, setupData, base.Dependency);
		case SetupTargetType.Ambulance:
			return m_HealthcarePathfindSetup.SetupAmbulances(this, setupData, base.Dependency);
		case SetupTargetType.Hospital:
			return m_HealthcarePathfindSetup.SetupHospitals(this, setupData, base.Dependency);
		case SetupTargetType.Hearse:
			return m_HealthcarePathfindSetup.SetupHearses(this, setupData, base.Dependency);
		case SetupTargetType.HealthcareRequest:
			return m_HealthcarePathfindSetup.SetupHealthcareRequest(this, setupData, base.Dependency);
		case SetupTargetType.AreaLocation:
			return m_AreaPathfindSetup.SetupAreaLocation(this, setupData, base.Dependency);
		case SetupTargetType.WoodResource:
			return m_AreaPathfindSetup.SetupWoodResource(this, setupData, base.Dependency);
		case SetupTargetType.Maintenance:
			return m_RoadPathfindSetup.SetupMaintenanceProviders(this, setupData, base.Dependency);
		case SetupTargetType.RandomTraffic:
			return m_RoadPathfindSetup.SetupRandomTraffic(this, setupData, base.Dependency);
		case SetupTargetType.OutsideConnection:
			return m_RoadPathfindSetup.SetupOutsideConnections(this, setupData, base.Dependency);
		case SetupTargetType.MaintenanceRequest:
			return m_RoadPathfindSetup.SetupMaintenanceRequest(this, setupData, base.Dependency);
		case SetupTargetType.TouristFindTarget:
			return m_CitizenPathfindSetup.SetupTouristTarget(this, setupData, base.Dependency);
		case SetupTargetType.Leisure:
			return m_CitizenPathfindSetup.SetupLeisureTarget(this, setupData, base.Dependency);
		case SetupTargetType.SchoolSeekerTo:
			return m_CitizenPathfindSetup.SetupSchoolSeekerTo(this, setupData, base.Dependency);
		case SetupTargetType.JobSeekerTo:
			return m_CitizenPathfindSetup.SetupJobSeekerTo(this, setupData, base.Dependency);
		case SetupTargetType.Attraction:
			return m_CitizenPathfindSetup.SetupAttraction(this, setupData, base.Dependency);
		case SetupTargetType.HomelessShelter:
			return m_CitizenPathfindSetup.SetupHomeless(this, setupData, base.Dependency);
		case SetupTargetType.FindHome:
			return m_CitizenPathfindSetup.SetupFindHome(this, setupData, base.Dependency);
		case SetupTargetType.Sightseeing:
			return default(JobHandle);
		case SetupTargetType.ResourceSeller:
			return m_ResourcePathfindSetup.SetupResourceSeller(this, setupData, base.Dependency);
		case SetupTargetType.ResourceExport:
			return m_ResourcePathfindSetup.SetupResourceExport(this, setupData, base.Dependency);
		case SetupTargetType.StorageTransfer:
			return m_ResourcePathfindSetup.SetupStorageTransfer(this, setupData, base.Dependency);
		default:
			UnityEngine.Debug.LogWarning("Invalid target type in Pathfind setup " + targetType);
			return default(JobHandle);
		}
	}
```

- `private FindTargets(Game.Pathfind.SetupTargetType targetType, Game.Simulation.PathfindSetupSystem+SetupData& setupData) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FindTargets(SetupTargetType targetType, in SetupData setupData)
	{
		switch (targetType)
		{
		case SetupTargetType.CurrentLocation:
			return m_CommonPathfindSetup.SetupCurrentLocation(this, setupData, base.Dependency);
		case SetupTargetType.AccidentLocation:
			return m_CommonPathfindSetup.SetupAccidentLocation(this, setupData, base.Dependency);
		case SetupTargetType.Safety:
			return m_CommonPathfindSetup.SetupSafety(this, setupData, base.Dependency);
		case SetupTargetType.PostVan:
			return m_PostServicePathfindSetup.SetupPostVans(this, setupData, base.Dependency);
		case SetupTargetType.MailTransfer:
			return m_PostServicePathfindSetup.SetupMailTransfer(this, setupData, base.Dependency);
		case SetupTargetType.MailBox:
			return m_PostServicePathfindSetup.SetupMailBoxes(this, setupData, base.Dependency);
		case SetupTargetType.PostVanRequest:
			return m_PostServicePathfindSetup.SetupPostVanRequest(this, setupData, base.Dependency);
		case SetupTargetType.GarbageCollector:
			return m_GarbagePathfindSetup.SetupGarbageCollector(this, setupData, base.Dependency);
		case SetupTargetType.GarbageTransfer:
			return m_GarbagePathfindSetup.SetupGarbageTransfer(this, setupData, base.Dependency);
		case SetupTargetType.GarbageCollectorRequest:
			return m_GarbagePathfindSetup.SetupGarbageCollectorRequest(this, setupData, base.Dependency);
		case SetupTargetType.Taxi:
			return m_TransportPathfindSetup.SetupTaxi(this, setupData, base.Dependency);
		case SetupTargetType.TransportVehicle:
			return m_TransportPathfindSetup.SetupTransportVehicle(this, setupData, base.Dependency);
		case SetupTargetType.RouteWaypoints:
			return m_TransportPathfindSetup.SetupRouteWaypoints(this, setupData, base.Dependency);
		case SetupTargetType.TransportVehicleRequest:
			return m_TransportPathfindSetup.SetupTransportVehicleRequest(this, setupData, base.Dependency);
		case SetupTargetType.TaxiRequest:
			return m_TransportPathfindSetup.SetupTaxiRequest(this, setupData, base.Dependency);
		case SetupTargetType.CrimeProducer:
			return m_PolicePathfindSetup.SetupCrimeProducer(this, setupData, base.Dependency);
		case SetupTargetType.PolicePatrol:
			return m_PolicePathfindSetup.SetupPolicePatrols(this, setupData, base.Dependency);
		case SetupTargetType.PrisonerTransport:
			return m_PolicePathfindSetup.SetupPrisonerTransport(this, setupData, base.Dependency);
		case SetupTargetType.PrisonerTransportRequest:
			return m_PolicePathfindSetup.SetupPrisonerTransportRequest(this, setupData, base.Dependency);
		case SetupTargetType.PoliceRequest:
			return m_PolicePathfindSetup.SetupPoliceRequest(this, setupData, base.Dependency);
		case SetupTargetType.EmergencyShelter:
			return m_FirePathfindSetup.SetupEmergencyShelters(this, setupData, base.Dependency);
		case SetupTargetType.EvacuationTransport:
			return m_FirePathfindSetup.SetupEvacuationTransport(this, setupData, base.Dependency);
		case SetupTargetType.FireEngine:
			return m_FirePathfindSetup.SetupFireEngines(this, setupData, base.Dependency);
		case SetupTargetType.EvacuationRequest:
			return m_FirePathfindSetup.SetupEvacuationRequest(this, setupData, base.Dependency);
		case SetupTargetType.FireRescueRequest:
			return m_FirePathfindSetup.SetupFireRescueRequest(this, setupData, base.Dependency);
		case SetupTargetType.Ambulance:
			return m_HealthcarePathfindSetup.SetupAmbulances(this, setupData, base.Dependency);
		case SetupTargetType.Hospital:
			return m_HealthcarePathfindSetup.SetupHospitals(this, setupData, base.Dependency);
		case SetupTargetType.Hearse:
			return m_HealthcarePathfindSetup.SetupHearses(this, setupData, base.Dependency);
		case SetupTargetType.HealthcareRequest:
			return m_HealthcarePathfindSetup.SetupHealthcareRequest(this, setupData, base.Dependency);
		case SetupTargetType.AreaLocation:
			return m_AreaPathfindSetup.SetupAreaLocation(this, setupData, base.Dependency);
		case SetupTargetType.WoodResource:
			return m_AreaPathfindSetup.SetupWoodResource(this, setupData, base.Dependency);
		case SetupTargetType.Maintenance:
			return m_RoadPathfindSetup.SetupMaintenanceProviders(this, setupData, base.Dependency);
		case SetupTargetType.RandomTraffic:
			return m_RoadPathfindSetup.SetupRandomTraffic(this, setupData, base.Dependency);
		case SetupTargetType.OutsideConnection:
			return m_RoadPathfindSetup.SetupOutsideConnections(this, setupData, base.Dependency);
		case SetupTargetType.MaintenanceRequest:
			return m_RoadPathfindSetup.SetupMaintenanceRequest(this, setupData, base.Dependency);
		case SetupTargetType.TouristFindTarget:
			return m_CitizenPathfindSetup.SetupTouristTarget(this, setupData, base.Dependency);
		case SetupTargetType.Leisure:
			return m_CitizenPathfindSetup.SetupLeisureTarget(this, setupData, base.Dependency);
		case SetupTargetType.SchoolSeekerTo:
			return m_CitizenPathfindSetup.SetupSchoolSeekerTo(this, setupData, base.Dependency);
		case SetupTargetType.JobSeekerTo:
			return m_CitizenPathfindSetup.SetupJobSeekerTo(this, setupData, base.Dependency);
		case SetupTargetType.Attraction:
			return m_CitizenPathfindSetup.SetupAttraction(this, setupData, base.Dependency);
		case SetupTargetType.HomelessShelter:
			return m_CitizenPathfindSetup.SetupHomeless(this, setupData, base.Dependency);
		case SetupTargetType.FindHome:
			return m_CitizenPathfindSetup.SetupFindHome(this, setupData, base.Dependency);
		case SetupTargetType.Sightseeing:
			return default(JobHandle);
		case SetupTargetType.ResourceSeller:
			return m_ResourcePathfindSetup.SetupResourceSeller(this, setupData, base.Dependency);
		case SetupTargetType.ResourceExport:
			return m_ResourcePathfindSetup.SetupResourceExport(this, setupData, base.Dependency);
		case SetupTargetType.StorageTransfer:
			return m_ResourcePathfindSetup.SetupStorageTransfer(this, setupData, base.Dependency);
		default:
			UnityEngine.Debug.LogWarning("Invalid target type in Pathfind setup " + targetType);
			return default(JobHandle);
		}
	}
```

- `public GetQueue(System.Object system, System.Int32 maxDelayFrames, System.Int32 spreadFrames = 0) : Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem>`  

```csharp
public NativeQueue<SetupQueueItem> GetQueue(object system, int maxDelayFrames, int spreadFrames = 0)
	{
		SetupQueue item;
		if (m_FreeQueues.Count != 0)
		{
			item = m_FreeQueues[m_FreeQueues.Count - 1];
			m_FreeQueues.RemoveAt(m_FreeQueues.Count - 1);
		}
		else
		{
			item = new SetupQueue
			{
				m_Queue = new NativeQueue<SetupQueueItem>(Allocator.Persistent)
			};
		}
		item.m_ResultFrame = m_SimulationSystem.frameIndex + (uint)maxDelayFrames;
		item.m_SpreadFrame = m_SimulationSystem.frameIndex + (uint)spreadFrames;
		if (item.m_ResultFrame < m_SimulationSystem.frameIndex)
		{
			item.m_ResultFrame = uint.MaxValue;
		}
		m_QueueSimulationFrameIndex = math.min(m_QueueSimulationFrameIndex, item.m_ResultFrame);
		item.m_System = system;
		m_ActiveQueues.Add(item);
		return item.m_Queue;
	}
```

- `public GetSetupQuery(Unity.Entities.EntityQueryDesc[] entityQueryDesc) : Unity.Entities.EntityQuery`  

```csharp
public EntityQuery GetSetupQuery(params ComponentType[] componentTypes)
	{
		return GetEntityQuery(componentTypes);
	}
```

- `public GetSetupQuery(Unity.Entities.ComponentType[] componentTypes) : Unity.Entities.EntityQuery`  

```csharp
public EntityQuery GetSetupQuery(params ComponentType[] componentTypes)
	{
		return GetEntityQuery(componentTypes);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TargetSeekerData = new PathfindTargetSeekerData(this);
		m_CommonPathfindSetup = new CommonPathfindSetup(this);
		m_PostServicePathfindSetup = new PostServicePathfindSetup(this);
		m_GarbagePathfindSetup = new GarbagePathfindSetup(this);
		m_TransportPathfindSetup = new TransportPathfindSetup(this);
		m_PolicePathfindSetup = new PolicePathfindSetup(this);
		m_FirePathfindSetup = new FirePathfindSetup(this);
		m_HealthcarePathfindSetup = new HealthcarePathfindSetup(this);
		m_AreaPathfindSetup = new AreaPathfindSetup(this);
		m_RoadPathfindSetup = new RoadPathfindSetup(this);
		m_CitizenPathfindSetup = new CitizenPathfindSetup(this);
		m_ResourcePathfindSetup = new ResourcePathfindSetup(this);
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_SetupList = new NativeList<SetupListItem>(100, Allocator.Persistent);
		m_ActiveQueues = new List<SetupQueue>(10);
		m_FreeQueues = new List<SetupQueue>(10);
		m_ActionList = new List<ActionListItem>(50);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_QueueDependencies.Complete();
		for (int i = 0; i < m_ActiveQueues.Count; i++)
		{
			m_ActiveQueues[i].m_Queue.Dispose();
		}
		for (int j = 0; j < m_FreeQueues.Count; j++)
		{
			m_FreeQueues[j].m_Queue.Dispose();
		}
		m_ActiveQueues.Clear();
		m_FreeQueues.Clear();
		m_SetupDependencies.Complete();
		for (int k = 0; k < m_SetupList.Length; k++)
		{
			m_SetupList[k].m_Buffer.Dispose();
		}
		for (int l = 0; l < m_ActionList.Count; l++)
		{
			m_ActionList[l].m_Action.Dispose();
		}
		m_SetupList.Dispose();
		m_ActionList.Clear();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ActiveQueues.Count == 0)
		{
			return;
		}
		CompleteSetup();
		m_TargetSeekerData.Update(this, m_AirwaySystem.GetAirwayData());
		m_QueueDependencies.Complete();
		m_QueueDependencies = default(JobHandle);
		int num = 0;
		for (int i = 0; i < m_ActiveQueues.Count; i++)
		{
			SetupQueue setupQueue = m_ActiveQueues[i];
			int num2 = int.MaxValue;
			if (setupQueue.m_SpreadFrame > m_SimulationSystem.frameIndex)
			{
				float num3 = ((m_SimulationSystem.smoothSpeed == 0f) ? 1f : (UnityEngine.Time.deltaTime * m_SimulationSystem.smoothSpeed * 60f));
				float num4 = (float)(setupQueue.m_SpreadFrame - m_SimulationSystem.frameIndex) + num3;
				num2 = (int)math.ceil((float)setupQueue.m_Queue.Count * (num3 / num4));
			}
			SetupQueueItem item;
			while (num2-- != 0 && setupQueue.m_Queue.TryDequeue(out item))
			{
				if (item.m_Parameters.m_ParkingTarget != Entity.Null && base.EntityManager.HasComponent<ConnectionLane>(item.m_Parameters.m_ParkingTarget))
				{
					item.m_Parameters.m_ParkingDelta = -1f;
				}
				PathfindAction action = new PathfindAction(0, 0, Allocator.Persistent, item.m_Parameters, item.m_Origin.m_Type, item.m_Destination.m_Type);
				m_SetupList.Add(new SetupListItem(item.m_Origin, item.m_Parameters, item.m_Owner, RandomSeed.Next(), m_ActionList.Count, actionStart: true));
				m_SetupList.Add(new SetupListItem(item.m_Destination, item.m_Parameters, item.m_Owner, RandomSeed.Next(), m_ActionList.Count, actionStart: false));
				m_ActionList.Add(new ActionListItem(action, item.m_Owner, setupQueue.m_ResultFrame, setupQueue.m_System));
			}
			if (setupQueue.m_Queue.IsEmpty())
			{
				m_FreeQueues.Add(setupQueue);
			}
			else
			{
				m_ActiveQueues[num++] = setupQueue;
			}
		}
		if (m_ActiveQueues.Count > num)
		{
			m_ActiveQueues.RemoveRange(num, m_ActiveQueues.Count - num);
		}
		if (m_SetupList.Length == 0)
		{
			m_QueueSimulationFrameIndex = uint.MaxValue;
			return;
		}
		m_SetupList.Sort();
		m_SetupSimulationFrameIndex = m_QueueSimulationFrameIndex;
		m_QueueSimulationFrameIndex = uint.MaxValue;
		m_PendingRequestCount = m_ActionList.Count;
		int num5 = 0;
		int j = 1;
		SetupTargetType setupTargetType = m_SetupList[num5].m_Target.m_Type;
		for (; j < m_SetupList.Length; j++)
		{
			SetupTargetType type = m_SetupList[j].m_Target.m_Type;
			if (setupTargetType != type)
			{
				FindTargets(num5, j);
				num5 = j;
				setupTargetType = type;
			}
		}
		FindTargets(num5, j);
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_QueueDependencies.Complete();
		for (int i = 0; i < m_ActiveQueues.Count; i++)
		{
			m_ActiveQueues[i].m_Queue.Dispose();
		}
		for (int j = 0; j < m_FreeQueues.Count; j++)
		{
			m_FreeQueues[j].m_Queue.Dispose();
		}
		m_ActiveQueues.Clear();
		m_FreeQueues.Clear();
		m_SetupDependencies.Complete();
		for (int k = 0; k < m_SetupList.Length; k++)
		{
			m_SetupList[k].m_Buffer.Dispose();
		}
		for (int l = 0; l < m_ActionList.Count; l++)
		{
			m_ActionList[l].m_Action.Dispose();
		}
		m_SetupList.Clear();
		m_ActionList.Clear();
		m_QueueSimulationFrameIndex = uint.MaxValue;
		m_SetupSimulationFrameIndex = uint.MaxValue;
		m_PendingRequestCount = 0;
	}
```


## Nested types

- `Game.Simulation.PathfindSetupSystem+SetupData`  
- `Game.Simulation.PathfindSetupSystem+SetupListItem`  
- `Game.Simulation.PathfindSetupSystem+ActionListItem`  
- `Game.Simulation.PathfindSetupSystem+SetupQueue`  
- `Game.Simulation.PathfindSetupSystem+DequePathTargetsJob`  

