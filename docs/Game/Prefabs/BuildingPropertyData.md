# Game.Prefabs.BuildingPropertyData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_ResidentialProperties`  
- `public Game.Economy.Resource m_AllowedSold`  
- `public Game.Economy.Resource m_AllowedInput`  
- `public Game.Economy.Resource m_AllowedManufactured`  
- `public Game.Economy.Resource m_AllowedStored`  
- `public System.Single m_SpaceMultiplier`  

## Methods

- `public CountProperties(Game.Zones.AreaType areaType) : System.Int32`  
- `public CountProperties() : System.Int32`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

