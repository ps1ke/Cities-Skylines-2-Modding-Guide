# Game.Simulation.IndustrialFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialFindPropertySystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Unity.Entities.EntityQuery m_IndustryQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Entities.EntityQuery m_FreePropertyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ZonePreferenceQuery;
    private Unity.Entities.EntityQuery m_FreeExtractorQuery;
    private Unity.Entities.EntityQuery m_CompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle;

    public IndustrialFindPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> propertiesOnMarket, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> workplaceDatas, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.EconomyParameterData economyParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, System.Boolean storage);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Unity.Entities.EntityQuery m_IndustryQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustryQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreePropertyQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ZonePreferenceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZonePreferenceQuery;
```

- `private Unity.Entities.EntityQuery m_FreeExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialFindPropertySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IndustrialFindPropertySystem()`  

```csharp
public IndustrialFindPropertySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> propertiesOnMarket, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> workplaceDatas, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.EconomyParameterData economyParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, System.Boolean storage) : System.Single`  

```csharp
public static System.Single Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> propertiesOnMarket, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.WorkplaceData> workplaceDatas, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Game.Prefabs.EconomyParameterData economyParameters, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, System.Boolean storage);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.IndustrialFindPropertySystem+TypeHandle`  

