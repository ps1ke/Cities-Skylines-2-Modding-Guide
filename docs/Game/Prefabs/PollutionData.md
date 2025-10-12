# Game.Prefabs.PollutionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PollutionData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Single m_GroundPollution`  
- `public System.Single m_AirPollution`  
- `public System.Single m_NoisePollution`  
- `public System.Boolean m_ScaleWithRenters`  

## Methods

- `public AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public Combine(Game.Prefabs.PollutionData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetValue(Game.Prefabs.BuildingStatusType statusType) : System.Single`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

