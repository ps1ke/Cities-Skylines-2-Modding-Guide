# Game.Vehicles.ParkedVehiclesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkedVehiclesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
    private Unity.Entities.EntityQuery m_PoliceCarQuery;
    private Unity.Entities.EntityQuery m_FireEngineQuery;
    private Unity.Entities.EntityQuery m_HealthcareVehicleQuery;
    private Unity.Entities.EntityQuery m_TransportVehicleQuery;
    private Unity.Entities.EntityQuery m_PostVanQuery;
    private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery;
    private Unity.Entities.EntityQuery m_GarbageTruckQuery;
    private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData;
    private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData;
    private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Game.Prefabs.PostVanSelectData m_PostVanSelectData;
    private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
    private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
    private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle;

    public ParkedVehiclesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CollectDeletedVehicles(Unity.Collections.NativeParallelMultiHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deletedVehicleMap, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void DuplicateVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private static Unity.Entities.Entity FindDeletedVehicle(Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Objects.Transform transform, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedMap);
    private System.Void FindParkingLocations(Unity.Entities.Entity entity, Unity.Collections.NativeList`1[[Game.Vehicles.ParkedVehiclesSystem+ParkingLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLocations, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& parkingLocationDeps);
    private static Unity.Mathematics.float4 GetMaxVehicleSize(Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Net.RoadTypes roadType);
    private static Unity.Entities.Entity GetSecondaryPrefab(Unity.Entities.Entity primaryPrefab, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layoutElements, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabDatas, System.Boolean& validLayout);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private static System.Boolean SelectParkingSpace(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Objects.Transform& transform, Unity.Entities.Entity& lane, System.Single& curvePosition);
    private System.Void SpawnFireEngines(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnGarbageTrucks(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnHealthcareVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnMaintenanceVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnPoliceCars(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnPostVans(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
    private System.Void SpawnTransportVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceCarQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceCarQuery;
```

- `private Unity.Entities.EntityQuery m_FireEngineQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireEngineQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_TransportVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_PostVanQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostVanQuery;
```

- `private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageTruckQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageTruckQuery;
```

- `private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData`  

```csharp
private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData;
```

- `private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData`  

```csharp
private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData;
```

- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  

```csharp
private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Game.Prefabs.PostVanSelectData m_PostVanSelectData`  

```csharp
private Game.Prefabs.PostVanSelectData m_PostVanSelectData;
```

- `private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData`  

```csharp
private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
```

- `private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData`  

```csharp
private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
```

- `private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ParkedVehiclesSystem()`  

```csharp
public ParkedVehiclesSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CollectDeletedVehicles(Unity.Collections.NativeParallelMultiHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deletedVehicleMap, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void CollectDeletedVehicles(Unity.Collections.NativeParallelMultiHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deletedVehicleMap, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private DuplicateVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void DuplicateVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private static FindDeletedVehicle(Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Objects.Transform transform, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedMap) : Unity.Entities.Entity`  

```csharp
private static Unity.Entities.Entity FindDeletedVehicle(Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Objects.Transform transform, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedMap);
```

- `private FindParkingLocations(Unity.Entities.Entity entity, Unity.Collections.NativeList`1[[Game.Vehicles.ParkedVehiclesSystem+ParkingLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLocations, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& parkingLocationDeps) : System.Void`  

```csharp
private System.Void FindParkingLocations(Unity.Entities.Entity entity, Unity.Collections.NativeList`1[[Game.Vehicles.ParkedVehiclesSystem+ParkingLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLocations, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& parkingLocationDeps);
```

- `private static GetMaxVehicleSize(Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Net.RoadTypes roadType) : Unity.Mathematics.float4`  

```csharp
private static Unity.Mathematics.float4 GetMaxVehicleSize(Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Net.RoadTypes roadType);
```

- `private static GetSecondaryPrefab(Unity.Entities.Entity primaryPrefab, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layoutElements, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabDatas, System.Boolean& validLayout) : Unity.Entities.Entity`  

```csharp
private static Unity.Entities.Entity GetSecondaryPrefab(Unity.Entities.Entity primaryPrefab, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layoutElements, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabDatas, System.Boolean& validLayout);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private static SelectParkingSpace(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Objects.Transform& transform, Unity.Entities.Entity& lane, System.Single& curvePosition) : System.Boolean`  

```csharp
private static System.Boolean SelectParkingSpace(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Objects.Transform& transform, Unity.Entities.Entity& lane, System.Single& curvePosition);
```

- `private SpawnFireEngines(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnFireEngines(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private SpawnGarbageTrucks(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnGarbageTrucks(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private SpawnHealthcareVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnHealthcareVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private SpawnMaintenanceVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnMaintenanceVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private SpawnPoliceCars(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnPoliceCars(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private SpawnPostVans(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnPostVans(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```

- `private SpawnTransportVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

```csharp
private System.Void SpawnTransportVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps);
```


## Nested types

- `Game.Vehicles.ParkedVehiclesSystem+ParkingLocation`  
- `Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData`  
- `Game.Vehicles.ParkedVehiclesSystem+FindParkingLocationsJob`  
- `Game.Vehicles.ParkedVehiclesSystem+CollectDeletedVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+DuplicateVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnPoliceCarsJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnFireEnginesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnHealthcareVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnTransportVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnPostVansJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnMaintenanceVehiclesJob`  
- `Game.Vehicles.ParkedVehiclesSystem+SpawnGarbageTrucksJob`  
- `Game.Vehicles.ParkedVehiclesSystem+TypeHandle`  

