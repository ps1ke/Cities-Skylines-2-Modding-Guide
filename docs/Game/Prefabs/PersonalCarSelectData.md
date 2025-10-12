# Game.Prefabs.PersonalCarSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  
- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PersonalCarData> m_PersonalCarDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.MovingObjectData> m_MovingObjectDataType`  

## Constructors

- `public PersonalCarSelectData(Unity.Entities.SystemBase system)`  

## Methods

- `private CalculateProbability(System.Int32 passengerAmount, System.Int32 baggageAmount, Game.Prefabs.PersonalCarSelectData+CarData firstData, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Int32& probability, System.Int32& offset) : System.Void`  
- `private CheckTractors(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData secondData, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset) : System.Void`  
- `private CheckTrailers(System.Int32 passengerAmount, System.Int32 baggageAmount, System.Int32 extraOffset, Game.Prefabs.PersonalCarSelectData+CarData firstData, System.Boolean emptyOnly, System.Boolean noSlowVehicles, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond, System.Int32& totalProbability, System.Int32& bestOffset) : System.Void`  
- `public CreateTrailer(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean noSlowVehicles, Unity.Entities.Entity tractorPrefab, Game.Objects.Transform tractorTransform, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay, Unity.Entities.Entity& trailer, Unity.Entities.Entity& vehiclePrefab, Unity.Entities.Entity& trailerPrefab) : Unity.Entities.Entity`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay = 0) : Unity.Entities.Entity`  
- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay) : Unity.Entities.Entity`  
- `private CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Prefabs.PersonalCarSelectData+CarData data, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state, System.Boolean stopped, System.UInt32 delay) : Unity.Entities.Entity`  
- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `private GetVehicleData(Unity.Mathematics.Random& random, System.Int32 passengerAmount, System.Int32 baggageAmount, System.Boolean avoidTrailers, System.Boolean noSlowVehicles, Game.Prefabs.PersonalCarSelectData+CarData& bestFirst, Game.Prefabs.PersonalCarSelectData+CarData& bestSecond) : System.Boolean`  
- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32 offset, System.Int32& totalProbability, System.Int32& bestOffset) : System.Boolean`  
- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

## Nested types

- `Game.Prefabs.PersonalCarSelectData+CarData`  

