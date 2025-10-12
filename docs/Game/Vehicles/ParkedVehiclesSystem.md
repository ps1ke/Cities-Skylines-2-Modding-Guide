# Game.Vehicles.ParkedVehiclesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_DeletedVehicleQuery`  
- `private Unity.Entities.EntityQuery m_PoliceCarQuery`  
- `private Unity.Entities.EntityQuery m_FireEngineQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareVehicleQuery`  
- `private Unity.Entities.EntityQuery m_TransportVehicleQuery`  
- `private Unity.Entities.EntityQuery m_PostVanQuery`  
- `private Unity.Entities.EntityQuery m_MaintenanceVehicleQuery`  
- `private Unity.Entities.EntityQuery m_GarbageTruckQuery`  
- `private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData`  
- `private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData`  
- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  
- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  
- `private Game.Prefabs.PostVanSelectData m_PostVanSelectData`  
- `private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData`  
- `private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData`  
- `private Game.Vehicles.ParkedVehiclesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ParkedVehiclesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CollectDeletedVehicles(Unity.Collections.NativeParallelMultiHashMap`2[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deletedVehicleMap, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private DuplicateVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private static FindDeletedVehicle(Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Objects.Transform transform, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedMap) : Unity.Entities.Entity`  
- `private FindParkingLocations(Unity.Entities.Entity entity, Unity.Collections.NativeList`1[[Game.Vehicles.ParkedVehiclesSystem+ParkingLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLocations, Unity.Jobs.JobHandle inputDeps, Unity.Jobs.JobHandle& parkingLocationDeps) : System.Void`  
- `private static GetMaxVehicleSize(Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Net.RoadTypes roadType) : Unity.Mathematics.float4`  
- `private static GetSecondaryPrefab(Unity.Entities.Entity primaryPrefab, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layoutElements, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabDatas, System.Boolean& validLayout) : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private static SelectParkingSpace(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> locations, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Objects.Transform& transform, Unity.Entities.Entity& lane, System.Single& curvePosition) : System.Boolean`  
- `private SpawnFireEngines(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private SpawnGarbageTrucks(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private SpawnHealthcareVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private SpawnMaintenanceVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private SpawnPoliceCars(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private SpawnPostVans(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  
- `private SpawnTransportVehicles(Unity.Entities.Entity entity, Game.Tools.Temp temp, System.Boolean isTemp, Unity.Collections.NativeList<Game.Vehicles.ParkedVehiclesSystem+ParkingLocation> parkingLocations, Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, Game.Vehicles.ParkedVehiclesSystem+DeletedVehicleData> deletedVehicleMap, Unity.Jobs.JobHandle& parkingLocationDeps, Unity.Jobs.JobHandle& deletedVehiclesDeps) : System.Void`  

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

