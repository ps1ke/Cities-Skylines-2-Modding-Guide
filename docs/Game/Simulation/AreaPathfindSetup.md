# Game.Simulation.AreaPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.ComponentLookup<Game.Objects.Tree> m_TreeData`  
- `private Unity.Entities.ComponentLookup<Game.Objects.Secondary> m_SecondaryData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportStationData> m_CargoTransportStationData`  
- `private Unity.Entities.BufferLookup<Game.Objects.SubObject> m_SubObjects`  
- `private Unity.Entities.BufferLookup<Game.Areas.WoodResource> m_WoodResources`  
- `private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  
- `private Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

## Constructors

- `public AreaPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupAreaLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupWoodResource(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.AreaPathfindSetup+SetupAreaLocationJob`  
- `Game.Simulation.AreaPathfindSetup+SetupWoodResourceJob`  

