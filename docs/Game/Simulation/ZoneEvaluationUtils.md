# Game.Simulation.ZoneEvaluationUtils

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `System.Object`  

## Constructors

- `public ZoneEvaluationUtils()`  

## Methods

- `public static GetCommercialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Boolean lodging) : System.Single`  
- `private static GetFactor(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Net.AvailableResource resource) : System.Single`  
- `public static GetFactors(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, Unity.Collections.NativeList<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult> results, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single pollution, System.Single landvalue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> resourceDatas) : System.Void`  
- `public static GetResidentialScore(Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Single landValue, System.Single pollution) : System.Single`  
- `public static GetScore(Game.Zones.AreaType areaType, System.Boolean office, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos, Game.Prefabs.ZonePreferenceData& preferences, System.Boolean storage, Unity.Collections.NativeArray<System.Int32> resourceDemands, Game.Prefabs.BuildingPropertyData propertyData, System.Single pollution, System.Single landValue, Unity.Entities.DynamicBuffer<Game.Zones.ProcessEstimate> estimates, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  
- `private static GetStorageScore(Game.Economy.Resource resource, System.Single price, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, System.Single curvePos) : System.Single`  
- `private static GetTransportScore(Game.Economy.Resource allowedManufactured, Unity.Collections.NativeList<Game.Prefabs.IndustrialProcessData> processes, Unity.Entities.DynamicBuffer<Game.Net.ResourceAvailability> availabilities, Unity.Collections.NativeArray<System.Int32> resourceDemands, System.Single curvePos, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas) : System.Single`  

## Nested types

- `Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor`  
- `Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult`  

