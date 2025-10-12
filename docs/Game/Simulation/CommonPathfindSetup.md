# Game.Simulation.CommonPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathOwner> m_PathOwnerData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  
- `private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  
- `private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  
- `private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData`  
- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  
- `private Unity.Entities.BufferLookup<Game.Areas.SubArea> m_SubAreas`  
- `private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements`  

## Constructors

- `public CommonPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupAccidentLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupCurrentLocation(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupSafety(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.CommonPathfindSetup+SetupCurrentLocationJob`  
- `Game.Simulation.CommonPathfindSetup+SetupAccidentLocationJob`  
- `Game.Simulation.CommonPathfindSetup+SetupSafetyJob`  
- `Game.Simulation.CommonPathfindSetup+TargetIterator`  

