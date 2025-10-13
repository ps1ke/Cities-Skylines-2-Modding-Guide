# Game.PSI.Telemetry+GameplayData

**Assembly:** `Game`  
**Namespace:** `Game.PSI`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class GameplayData
{
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Unity.Entities.EntityQuery m_BuildingsQuery;
    private Unity.Entities.EntityQuery m_OwnedTileQuery;
    private Unity.Entities.EntityQuery m_FollowedQuery;
    private readonly Game.Prefabs.PrefabSystem m_PrefabSystem;
    private readonly Game.UI.InGame.TimeUISystem m_TimeSystem;
    private readonly Game.Simulation.SimulationSystem m_SimulationSystem;
    private readonly Game.UI.MapMetadataSystem m_MapMetadataSystem;
    private readonly Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private readonly Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private readonly Game.Tutorials.TutorialSystem m_TutorialSystem;
    private readonly Game.Simulation.CitySystem m_CitySystem;
    private readonly Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem;
    private readonly Game.Prefabs.Modes.GameModeSystem m_GameModeSystem;

    public System.Int32 buildingCount { get; }
    public Game.City.Population population { get; }
    public System.Int32 moneyAmount { get; }
    public System.Int32 moneyDelta { get; }
    public System.Int32 followedCitizens { get; }
    public System.Int32 ownedMapTiles { get; }
    public System.String mapName { get; }
    public System.Single simulationSpeed { get; }
    public System.Boolean unlimitedMoney { get; }
    public System.Boolean unlockAll { get; }
    public System.Boolean naturalDisasters { get; }
    public System.Boolean tutorialEnabled { get; }
    public System.String currentGameMode { get; }

    public GameplayData(Unity.Entities.World world);

    internal static Colossal.PSI.Common.IDlc <GetDLCsFromContent>g__CreateDummyDLC|29_0(Game.Prefabs.ContentPrefab contentPrefab);
    public System.Int32 GetDay();
    public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> GetDLCsFromContent();
    public T GetPrefab<T>(Unity.Entities.Entity entity);
    public System.Int32 GetResourcesOutputCount();
    private System.Void InitializeStats(Unity.Entities.World world);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_OwnedTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnedTileQuery;
```

- `private Unity.Entities.EntityQuery m_FollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FollowedQuery;
```

- `private readonly Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private readonly Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private readonly Game.UI.InGame.TimeUISystem m_TimeSystem`  

```csharp
private readonly Game.UI.InGame.TimeUISystem m_TimeSystem;
```

- `private readonly Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private readonly Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private readonly Game.UI.MapMetadataSystem m_MapMetadataSystem`  

```csharp
private readonly Game.UI.MapMetadataSystem m_MapMetadataSystem;
```

- `private readonly Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private readonly Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private readonly Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private readonly Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private readonly Game.Tutorials.TutorialSystem m_TutorialSystem`  

```csharp
private readonly Game.Tutorials.TutorialSystem m_TutorialSystem;
```

- `private readonly Game.Simulation.CitySystem m_CitySystem`  

```csharp
private readonly Game.Simulation.CitySystem m_CitySystem;
```

- `private readonly Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private readonly Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private readonly Game.Prefabs.Modes.GameModeSystem m_GameModeSystem`  

```csharp
private readonly Game.Prefabs.Modes.GameModeSystem m_GameModeSystem;
```


## Properties

- `public System.Int32 buildingCount { get }`  

```csharp
public System.Int32 buildingCount { get; }
```

- `public Game.City.Population population { get }`  

```csharp
public Game.City.Population population { get; }
```

- `public System.Int32 moneyAmount { get }`  

```csharp
public System.Int32 moneyAmount { get; }
```

- `public System.Int32 moneyDelta { get }`  

```csharp
public System.Int32 moneyDelta { get; }
```

- `public System.Int32 followedCitizens { get }`  

```csharp
public System.Int32 followedCitizens { get; }
```

- `public System.Int32 ownedMapTiles { get }`  

```csharp
public System.Int32 ownedMapTiles { get; }
```

- `public System.String mapName { get }`  

```csharp
public System.String mapName { get; }
```

- `public System.Single simulationSpeed { get }`  

```csharp
public System.Single simulationSpeed { get; }
```

- `public System.Boolean unlimitedMoney { get }`  

```csharp
public System.Boolean unlimitedMoney { get; }
```

- `public System.Boolean unlockAll { get }`  

```csharp
public System.Boolean unlockAll { get; }
```

- `public System.Boolean naturalDisasters { get }`  

```csharp
public System.Boolean naturalDisasters { get; }
```

- `public System.Boolean tutorialEnabled { get }`  

```csharp
public System.Boolean tutorialEnabled { get; }
```

- `public System.String currentGameMode { get }`  

```csharp
public System.String currentGameMode { get; }
```


## Constructors

- `public GameplayData(Unity.Entities.World world)`  

```csharp
public GameplayData(Unity.Entities.World world);
```


## Methods

- `internal static <GetDLCsFromContent>g__CreateDummyDLC|29_0(Game.Prefabs.ContentPrefab contentPrefab) : Colossal.PSI.Common.IDlc`  

```csharp
internal static Colossal.PSI.Common.IDlc <GetDLCsFromContent>g__CreateDummyDLC|29_0(Game.Prefabs.ContentPrefab contentPrefab);
```

- `public GetDay() : System.Int32`  

```csharp
public System.Int32 GetDay();
```

- `public GetDLCsFromContent() : System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc>`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.PSI.Common.IDlc> GetDLCsFromContent();
```

- `public GetPrefab<T>(Unity.Entities.Entity entity) : T`  

```csharp
public T GetPrefab<T>(Unity.Entities.Entity entity);
```

- `public GetResourcesOutputCount() : System.Int32`  

```csharp
public System.Int32 GetResourcesOutputCount();
```

- `private InitializeStats(Unity.Entities.World world) : System.Void`  

```csharp
private System.Void InitializeStats(Unity.Entities.World world);
```


