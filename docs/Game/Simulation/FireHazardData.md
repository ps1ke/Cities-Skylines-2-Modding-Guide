# Game.Simulation.EventHelpers+FireHazardData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct FireHazardData
{
    public Game.Buildings.LocalEffectSystem+ReadData m_LocalEffectData;
    public System.Single m_ForestFireHazardFactor;
    public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData;
    public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages;
    public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesData;

    public FireHazardData(Unity.Entities.SystemBase system);

    public System.Boolean GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Buildings.Building building, Game.Areas.CurrentDistrict currentDistrict, Game.Objects.Damaged damaged, Game.Objects.UnderConstruction underConstruction, System.Single& fireHazard, System.Single& riskFactor);
    public System.Boolean GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Objects.Tree tree, Game.Objects.Transform transform, Game.Objects.Damaged damaged, System.Single& fireHazard, System.Single& riskFactor);
    private System.Single GetFireHazard(Game.Prefabs.PrefabRef prefabRef);
    private System.Single GetFireHazardFactor(Game.Objects.Damaged damaged);
    public System.Void Update(Unity.Entities.SystemBase system, Game.Buildings.LocalEffectSystem+ReadData localEffectData, Game.Prefabs.FireConfigurationPrefab fireConfigurationPrefab, System.Single temperature, System.Single noRainDays);
}
```


## Fields

- `public Game.Buildings.LocalEffectSystem+ReadData m_LocalEffectData`  

```csharp
public Game.Buildings.LocalEffectSystem+ReadData m_LocalEffectData;
```

- `public System.Single m_ForestFireHazardFactor`  

```csharp
public System.Single m_ForestFireHazardFactor;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData;
```

- `public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages;
```

- `public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> m_DistrictModifiers;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ZonePropertiesData> m_ZonePropertiesData;
```


## Constructors

- `public FireHazardData(Unity.Entities.SystemBase system)`  

```csharp
public FireHazardData(Unity.Entities.SystemBase system);
```


## Methods

- `public GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Buildings.Building building, Game.Areas.CurrentDistrict currentDistrict, Game.Objects.Damaged damaged, Game.Objects.UnderConstruction underConstruction, System.Single& fireHazard, System.Single& riskFactor) : System.Boolean`  

```csharp
public System.Boolean GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Buildings.Building building, Game.Areas.CurrentDistrict currentDistrict, Game.Objects.Damaged damaged, Game.Objects.UnderConstruction underConstruction, System.Single& fireHazard, System.Single& riskFactor);
```

- `public GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Objects.Tree tree, Game.Objects.Transform transform, Game.Objects.Damaged damaged, System.Single& fireHazard, System.Single& riskFactor) : System.Boolean`  

```csharp
public System.Boolean GetFireHazard(Game.Prefabs.PrefabRef prefabRef, Game.Objects.Tree tree, Game.Objects.Transform transform, Game.Objects.Damaged damaged, System.Single& fireHazard, System.Single& riskFactor);
```

- `private GetFireHazard(Game.Prefabs.PrefabRef prefabRef) : System.Single`  

```csharp
private System.Single GetFireHazard(Game.Prefabs.PrefabRef prefabRef);
```

- `private GetFireHazardFactor(Game.Objects.Damaged damaged) : System.Single`  

```csharp
private System.Single GetFireHazardFactor(Game.Objects.Damaged damaged);
```

- `public Update(Unity.Entities.SystemBase system, Game.Buildings.LocalEffectSystem+ReadData localEffectData, Game.Prefabs.FireConfigurationPrefab fireConfigurationPrefab, System.Single temperature, System.Single noRainDays) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system, Game.Buildings.LocalEffectSystem+ReadData localEffectData, Game.Prefabs.FireConfigurationPrefab fireConfigurationPrefab, System.Single temperature, System.Single noRainDays);
```


