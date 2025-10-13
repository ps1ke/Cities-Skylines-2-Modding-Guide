# Game.Simulation.AreaPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AreaPathfindSetup
{
    private Unity.Entities.ComponentLookup<Game.Objects.Tree> m_TreeData;
    private Unity.Entities.ComponentLookup<Game.Objects.Secondary> m_SecondaryData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportStationData> m_CargoTransportStationData;
    private Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects;
    private Unity.Entities.BufferLookup<Game.Areas.WoodResource> m_WoodResources;
    private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
    private Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;

    public AreaPathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupAreaLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupWoodResource(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.ComponentLookup<Game.Objects.Tree> m_TreeData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.Tree> m_TreeData;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.Secondary> m_SecondaryData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.Secondary> m_SecondaryData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportStationData> m_CargoTransportStationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportStationData> m_CargoTransportStationData;
```

- `private Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects`  

```csharp
private Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects;
```

- `private Unity.Entities.BufferLookup<Game.Areas.WoodResource> m_WoodResources`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.WoodResource> m_WoodResources;
```

- `private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas;
```

- `private Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

```csharp
private Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
```


## Constructors

- `public AreaPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public AreaPathfindSetup(PathfindSetupSystem system)
	{
		m_TreeData = system.GetComponentLookup<Tree>(isReadOnly: true);
		m_SecondaryData = system.GetComponentLookup<Secondary>(isReadOnly: true);
		m_CargoTransportStationData = system.GetComponentLookup<CargoTransportStationData>(isReadOnly: true);
		m_SubObjects = system.GetBufferLookup<Game.Objects.SubObject>(isReadOnly: true);
		m_WoodResources = system.GetBufferLookup<WoodResource>(isReadOnly: true);
		m_SubAreas = system.GetBufferLookup<Game.Areas.SubArea>(isReadOnly: true);
		m_InstalledUpgrades = system.GetBufferLookup<InstalledUpgrade>(isReadOnly: true);
	}
```


## Methods

- `public SetupAreaLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupAreaLocation(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_SecondaryData.Update(system);
		m_CargoTransportStationData.Update(system);
		m_SubObjects.Update(system);
		m_SubAreas.Update(system);
		m_InstalledUpgrades.Update(system);
		return IJobParallelForExtensions.Schedule(new SetupAreaLocationJob
		{
			m_SecondaryData = m_SecondaryData,
			m_CargoTransportStationData = m_CargoTransportStationData,
			m_SubObjects = m_SubObjects,
			m_SubAreas = m_SubAreas,
			m_InstalledUpgrades = m_InstalledUpgrades,
			m_SetupData = setupData
		}, setupData.Length, 1, inputDeps);
	}
```

- `public SetupWoodResource(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupWoodResource(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_TreeData.Update(system);
		m_WoodResources.Update(system);
		m_SubAreas.Update(system);
		return IJobParallelForExtensions.Schedule(new SetupWoodResourceJob
		{
			m_TreeData = m_TreeData,
			m_WoodResources = m_WoodResources,
			m_SubAreas = m_SubAreas,
			m_SetupData = setupData
		}, setupData.Length, 1, inputDeps);
	}
```


## Nested types

- `Game.Simulation.AreaPathfindSetup+SetupAreaLocationJob`  
- `Game.Simulation.AreaPathfindSetup+SetupWoodResourceJob`  

