# Game.Simulation.CommercialFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommercialFindPropertySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CommerceQuery;
    private Unity.Entities.EntityQuery m_FreePropertyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_ZonePreferenceQuery;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle;

    public CommercialFindPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterBuffers, Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> companies, Game.Prefabs.ZonePreferenceData& preferences);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CommerceQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommerceQuery;
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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommercialFindPropertySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CommercialFindPropertySystem()`  

```csharp
public CommercialFindPropertySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterBuffers, Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> companies, Game.Prefabs.ZonePreferenceData& preferences) : System.Single`  

```csharp
public static System.Single Evaluate(Unity.Entities.Entity company, Unity.Entities.Entity property, Game.Companies.ServiceCompanyData& service, Game.Prefabs.IndustrialProcessData& process, Game.Agents.PropertySeeker& propertySeeker, Unity.Entities.ComponentLookup<Game.Buildings.Building> buildings, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabFromEntity, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> buildingDatas, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities, Unity.Entities.ComponentLookup<Game.Net.LandValue> landValues, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> propertyDatas, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterBuffers, Unity.Entities.ComponentLookup<Game.Companies.CommercialCompany> companies, Game.Prefabs.ZonePreferenceData& preferences);
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

- `Game.Simulation.CommercialFindPropertySystem+TypeHandle`  

