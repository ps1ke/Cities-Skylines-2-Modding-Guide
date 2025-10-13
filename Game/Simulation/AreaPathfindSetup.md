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
public AreaPathfindSetup(Game.Simulation.PathfindSetupSystem system);
```


## Methods

- `public SetupAreaLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupAreaLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupWoodResource(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupWoodResource(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Simulation.AreaPathfindSetup+SetupAreaLocationJob`  
- `Game.Simulation.AreaPathfindSetup+SetupWoodResourceJob`  

