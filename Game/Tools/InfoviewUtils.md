# Game.Tools.InfoviewUtils

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class InfoviewUtils
{
    public static System.Single GetColor(Game.Prefabs.InfoviewCoverageData data, System.Single coverage);
    public static System.Single GetColor(Game.Prefabs.InfoviewAvailabilityData data, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilityBuffer, System.Single curvePosition, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeArray<System.Int32> industrialDemands, Unity.Collections.NativeArray<System.Int32> storageDemands, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
    public static System.Single GetColor(Game.Prefabs.InfoviewNetStatusData data, System.Single status);
    public static System.Single GetColor(Game.Prefabs.InfoviewBuildingStatusData data, System.Single status);
    public static System.Single GetColor(Game.Prefabs.InfoviewObjectStatusData data, System.Single status);
}
```


## Methods

- `public static GetColor(Game.Prefabs.InfoviewCoverageData data, System.Single coverage) : System.Single`  

```csharp
public static System.Single GetColor(Game.Prefabs.InfoviewCoverageData data, System.Single coverage);
```

- `public static GetColor(Game.Prefabs.InfoviewAvailabilityData data, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilityBuffer, System.Single curvePosition, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeArray<System.Int32> industrialDemands, Unity.Collections.NativeArray<System.Int32> storageDemands, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Single`  

```csharp
public static System.Single GetColor(Game.Prefabs.InfoviewAvailabilityData data, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilityBuffer, System.Single curvePosition, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeArray<System.Int32> industrialDemands, Unity.Collections.NativeArray<System.Int32> storageDemands, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas);
```

- `public static GetColor(Game.Prefabs.InfoviewNetStatusData data, System.Single status) : System.Single`  

```csharp
public static System.Single GetColor(Game.Prefabs.InfoviewNetStatusData data, System.Single status);
```

- `public static GetColor(Game.Prefabs.InfoviewBuildingStatusData data, System.Single status) : System.Single`  

```csharp
public static System.Single GetColor(Game.Prefabs.InfoviewBuildingStatusData data, System.Single status);
```

- `public static GetColor(Game.Prefabs.InfoviewObjectStatusData data, System.Single status) : System.Single`  

```csharp
public static System.Single GetColor(Game.Prefabs.InfoviewObjectStatusData data, System.Single status);
```


