# Game.Simulation.CommonPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CommonPathfindSetup
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwnerData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
    private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
    private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData;
    private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
    private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements;

    public CommonPathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupAccidentLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupCurrentLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupSafety(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwnerData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwnerData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
```

- `private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
```

- `private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
```

- `private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData;
```

- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
```

- `private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
```

- `private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements;
```


## Constructors

- `public CommonPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public CommonPathfindSetup(PathfindSetupSystem system)
	{
		m_NetSearchSystem = system.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_PathOwnerData = system.GetComponentLookup<PathOwner>(isReadOnly: true);
		m_VehicleData = system.GetComponentLookup<Vehicle>(isReadOnly: true);
		m_CompositionData = system.GetComponentLookup<Composition>(isReadOnly: true);
		m_NetCompositionData = system.GetComponentLookup<NetCompositionData>(isReadOnly: true);
		m_CreatureData = system.GetComponentLookup<Creature>(isReadOnly: true);
		m_AccidentSiteData = system.GetComponentLookup<AccidentSite>(isReadOnly: true);
		m_PathElements = system.GetBufferLookup<PathElement>(isReadOnly: true);
		m_SubAreas = system.GetBufferLookup<Game.Areas.SubArea>(isReadOnly: true);
		m_TargetElements = system.GetBufferLookup<TargetElement>(isReadOnly: true);
	}
```


## Methods

- `public SetupAccidentLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupAccidentLocation(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_CreatureData.Update(system);
		m_VehicleData.Update(system);
		m_AccidentSiteData.Update(system);
		m_CompositionData.Update(system);
		m_NetCompositionData.Update(system);
		m_TargetElements.Update(system);
		m_SubAreas.Update(system);
		JobHandle dependencies;
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(new SetupAccidentLocationJob
		{
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_CreatureData = m_CreatureData,
			m_VehicleData = m_VehicleData,
			m_AccidentSiteData = m_AccidentSiteData,
			m_CompositionData = m_CompositionData,
			m_NetCompositionData = m_NetCompositionData,
			m_TargetElements = m_TargetElements,
			m_SubAreas = m_SubAreas,
			m_SetupData = setupData
		}, setupData.Length, 1, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupCurrentLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupCurrentLocation(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_PathOwnerData.Update(system);
		m_VehicleData.Update(system);
		m_CompositionData.Update(system);
		m_NetCompositionData.Update(system);
		m_PathElements.Update(system);
		m_SubAreas.Update(system);
		JobHandle dependencies;
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(new SetupCurrentLocationJob
		{
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_PathOwnerData = m_PathOwnerData,
			m_VehicleData = m_VehicleData,
			m_CompositionData = m_CompositionData,
			m_NetCompositionData = m_NetCompositionData,
			m_PathElements = m_PathElements,
			m_SubAreas = m_SubAreas,
			m_SetupData = setupData
		}, setupData.Length, 1, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupSafety(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupSafety(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_CompositionData.Update(system);
		m_NetCompositionData.Update(system);
		JobHandle dependencies;
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(new SetupSafetyJob
		{
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_CompositionData = m_CompositionData,
			m_NetCompositionData = m_NetCompositionData,
			m_SetupData = setupData
		}, setupData.Length, 1, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Simulation.CommonPathfindSetup+SetupCurrentLocationJob`  
- `Game.Simulation.CommonPathfindSetup+SetupAccidentLocationJob`  
- `Game.Simulation.CommonPathfindSetup+SetupSafetyJob`  
- `Game.Simulation.CommonPathfindSetup+TargetIterator`  

