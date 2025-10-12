# Game.Prefabs.WorkVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  
- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType`  

## Constructors

- `public WorkVehicleSelectData(Unity.Entities.SystemBase system)`  

## Methods

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  
- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  
- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Game.Prefabs.WorkVehicleSelectData+VehicleData forthData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  
- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  
- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  
- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass, Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state) : Unity.Entities.Entity`  
- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData data, Game.Vehicles.VehicleWorkType workType, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state) : Unity.Entities.Entity`  
- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  
- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

## Nested types

- `Game.Prefabs.WorkVehicleSelectData+VehicleData`  

