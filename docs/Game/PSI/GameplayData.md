# Game.PSI.Telemetry+GameplayData

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Unity.Entities.EntityQuery m_PopulationQuery`  
- `private Unity.Entities.EntityQuery m_BuildingsQuery`  
- `private Unity.Entities.EntityQuery m_OwnedTileQuery`  
- `private Unity.Entities.EntityQuery m_FollowedQuery`  
- `private readonly Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private readonly Game.UI.InGame.TimeUISystem m_TimeSystem`  
- `private readonly Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private readonly Game.UI.MapMetadataSystem m_MapMetadataSystem`  
- `private readonly Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private readonly Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private readonly Game.Tutorials.TutorialSystem m_TutorialSystem`  
- `private readonly Game.Simulation.CitySystem m_CitySystem`  
- `private readonly Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem`  
- `private readonly Game.Prefabs.Modes.GameModeSystem m_GameModeSystem`  

## Properties

- `public System.Int32 buildingCount { get }`  
- `public Game.City.Population population { get }`  
- `public System.Int32 moneyAmount { get }`  
- `public System.Int32 moneyDelta { get }`  
- `public System.Int32 followedCitizens { get }`  
- `public System.Int32 ownedMapTiles { get }`  
- `public System.String mapName { get }`  
- `public System.Single simulationSpeed { get }`  
- `public System.Boolean unlimitedMoney { get }`  
- `public System.Boolean unlockAll { get }`  
- `public System.Boolean naturalDisasters { get }`  
- `public System.Boolean tutorialEnabled { get }`  
- `public System.String currentGameMode { get }`  

## Constructors

- `public GameplayData(Unity.Entities.World world)`  

## Methods

- `internal static <GetDLCsFromContent>g__CreateDummyDLC|29_0(Game.Prefabs.ContentPrefab contentPrefab) : Colossal.PSI.Common.IDlc`  
- `public GetDay() : System.Int32`  
- `public GetDLCsFromContent() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  
- `public GetPrefab<T>(Unity.Entities.Entity entity) : T`  
- `public GetResourcesOutputCount() : System.Int32`  
- `private InitializeStats(Unity.Entities.World world) : System.Void`  

