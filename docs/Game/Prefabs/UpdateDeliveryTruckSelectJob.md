# Game.Prefabs.UpdateDeliveryTruckSelectJob

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  
- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  
- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  
- `public Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  
- `public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems`  

## Methods

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData) : System.Void`  
- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData) : System.Void`  
- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData forthData) : System.Void`  
- `private CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData) : System.Void`  
- `private CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData) : System.Void`  
- `private CheckTrailers(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData) : System.Void`  
- `public Execute() : System.Void`  

## Nested types

- `Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData`  

