# Game.Companies.StorageLimitData

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Game.Prefabs.ICombineData<Game.Companies.StorageLimitData>`  

## Fields

- `public System.Int32 m_Limit`  

## Methods

- `public Combine(Game.Companies.StorageLimitData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetAdjustedLimitForWarehouse(Game.Prefabs.SpawnableBuildingData spawnable, Game.Prefabs.BuildingData building) : System.Int32`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

