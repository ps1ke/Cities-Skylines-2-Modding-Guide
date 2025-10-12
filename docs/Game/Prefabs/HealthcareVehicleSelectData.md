# Game.Prefabs.HealthcareVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  
- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.AmbulanceData> m_AmbulanceType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HearseData> m_HearseType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.HelicopterData> m_HelicopterType`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.ObjectData> m_ObjectData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.MovingObjectData> m_MovingObjectData`  

## Constructors

- `public HealthcareVehicleSelectData(Unity.Entities.SystemBase system)`  

## Methods

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Simulation.HealthcareRequestType healthcareType, Game.Net.RoadTypes roadType, System.Boolean parked) : Unity.Entities.Entity`  
- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Objects.Transform transform, Unity.Entities.Entity source, Unity.Entities.Entity prefab, Game.Simulation.HealthcareRequestType healthcareType, Game.Net.RoadTypes roadType, System.Boolean parked) : Unity.Entities.Entity`  
- `private GetArchetype(Unity.Entities.Entity prefab, System.Boolean parked) : Unity.Entities.EntityArchetype`  
- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  
- `private GetRandomVehicle(Unity.Mathematics.Random& random, Game.Simulation.HealthcareRequestType healthcareType, Game.Net.RoadTypes roadType) : Unity.Entities.Entity`  
- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  
- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  
- `public SelectVehicle(Unity.Mathematics.Random& random, Game.Simulation.HealthcareRequestType healthcareType, Game.Net.RoadTypes roadType) : Unity.Entities.Entity`  

