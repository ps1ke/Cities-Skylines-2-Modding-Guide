# Game.Prefabs.TransportTrainCarriageSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  
- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CargoTransportVehicleData> m_CargoTransportVehicleType`  

## Constructors

- `public TransportTrainCarriageSelectData(Unity.Entities.SystemBase system)`  

## Methods

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  
- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  
- `public SelectCarriagePrefab(Unity.Mathematics.Random& random, Game.Economy.Resource resource, System.Int32 amount) : Unity.Entities.Entity`  

