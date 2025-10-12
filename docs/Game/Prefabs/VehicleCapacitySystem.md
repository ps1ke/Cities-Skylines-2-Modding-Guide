# Game.Prefabs.VehicleCapacitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_DeliveryTruckQuery`  
- `private Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems`  
- `private Unity.Jobs.JobHandle m_WriteDependency`  
- `private Game.Prefabs.VehicleSelectRequirementData m_VehicleSelectRequirementData`  
- `private System.Boolean m_RequireUpdate`  
- `private Game.Prefabs.VehicleCapacitySystem+TypeHandle __TypeHandle`  

## Constructors

- `public VehicleCapacitySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetDeliveryTruckSelectData() : Game.Prefabs.DeliveryTruckSelectData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Prefabs.VehicleCapacitySystem+TypeHandle`  

