# Game.Prefabs.TransportVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  
- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainData> m_TrainType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainEngineData> m_TrainEngineType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TrainCarriageData> m_TrainCarriageType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MultipleUnitTrainData> m_MultipleUnitTrainType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.TaxiData> m_TaxiType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AircraftData> m_AircraftType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AirplaneData> m_AirplaneType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftType`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.TrainObjectData> m_TrainObjectData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.PublicTransportVehicleData> m_PublicTransportVehicleData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleData`  
- `private Unity.Entities.BufferLookup<Game.Prefabs.VehicleCarriageElement> m_VehicleCarriages`  

## Constructors

- `public TransportVehicleSelectData(Unity.Entities.SystemBase system)`  

## Methods

- `private AddTransportComponents(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Unity.Entities.Entity entity) : System.Void`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked) : Unity.Entities.Entity`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity, System.Boolean parked, Unity.Collections.NativeList`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layout) : Unity.Entities.Entity`  
- `private GetArchetype(Unity.Entities.Entity prefab, System.Boolean controller, System.Boolean parked) : Unity.Entities.EntityArchetype`  
- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `private GetRandomVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity primaryPrefab, Unity.Entities.Entity secondaryPrefab, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs, System.Boolean ignoreTheme, System.Boolean& isMultipleUnitTrain, System.Int32& unitCount, Unity.Entities.Entity& secondaryResult, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity) : Unity.Entities.Entity`  
- `public ListVehicles(Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Collections.NativeList<Unity.Entities.Entity> primaryPrefabs, Unity.Collections.NativeList<Unity.Entities.Entity> secondaryPrefabs) : System.Void`  
- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 priority, System.Int32& totalProbability, System.Int32& selectedPriority) : System.Boolean`  
- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  
- `public SelectVehicle(Unity.Mathematics.Random& random, Game.Prefabs.TransportType transportType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Prefabs.PublicTransportPurpose publicTransportPurpose, Game.Economy.Resource cargoResources, Unity.Entities.Entity& primaryPrefab, Unity.Entities.Entity& secondaryPrefab, Unity.Mathematics.int2& passengerCapacity, Unity.Mathematics.int2& cargoCapacity) : System.Void`  

