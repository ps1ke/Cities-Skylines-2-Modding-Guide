# Game.Simulation.ZoneEvaluationUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ZoneEvaluationUtils
{
    public ZoneEvaluationUtils();

    public static System.Single GetCommercialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Boolean lodging);
    private static System.Single GetFactor(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Net.AvailableResource resource);
    public static System.Void GetFactors(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> results, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single pollution, System.Single landvalue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
    public static System.Single GetResidentialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Single pollution);
    public static System.Single GetScore(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Boolean storage, Unity.Collections.NativeArray<System.Int32> resourceDemands, Game.Prefabs.BuildingPropertyData propertyData, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
    private static System.Single GetStorageScore(Game.Economy.Resource resource, System.Single price, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos);
    private static System.Single GetTransportScore(Game.Economy.Resource allowedManufactured, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single curvePos, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
}
```


## Constructors

- `public ZoneEvaluationUtils()`  

```csharp
public ZoneEvaluationUtils();
```


## Methods

- `public static GetCommercialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Boolean lodging) : System.Single`  

```csharp
public static System.Single GetCommercialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Boolean lodging);
```

- `private static GetFactor(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Net.AvailableResource resource) : System.Single`  

```csharp
private static System.Single GetFactor(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Net.AvailableResource resource);
```

- `public static GetFactors(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> results, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single pollution, System.Single landvalue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Void`  

```csharp
public static System.Void GetFactors(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> results, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single pollution, System.Single landvalue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
```

- `public static GetResidentialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Single pollution) : System.Single`  

```csharp
public static System.Single GetResidentialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Single pollution);
```

- `public static GetScore(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Boolean storage, Unity.Collections.NativeArray<System.Int32> resourceDemands, Game.Prefabs.BuildingPropertyData propertyData, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
public static System.Single GetScore(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Boolean storage, Unity.Collections.NativeArray<System.Int32> resourceDemands, Game.Prefabs.BuildingPropertyData propertyData, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```

- `private static GetStorageScore(Game.Economy.Resource resource, System.Single price, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos) : System.Single`  

```csharp
private static System.Single GetStorageScore(Game.Economy.Resource resource, System.Single price, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos);
```

- `private static GetTransportScore(Game.Economy.Resource allowedManufactured, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single curvePos, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

```csharp
private static System.Single GetTransportScore(Game.Economy.Resource allowedManufactured, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single curvePos, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas);
```


## Nested types

- `Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor`  
- `Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult`  

