# Game.Prefabs.PlaceableNetData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public Colossal.Mathematics.Bounds1 m_ElevationRange`  
- `public Unity.Entities.Entity m_UndergroundPrefab`  
- `public Game.Net.PlacementFlags m_PlacementFlags`  
- `public Game.Prefabs.CompositionFlags m_SetUpgradeFlags`  
- `public Game.Prefabs.CompositionFlags m_UnsetUpgradeFlags`  
- `public System.UInt32 m_DefaultConstructionCost`  
- `public System.Single m_DefaultUpkeepCost`  
- `public System.Single m_SnapDistance`  
- `public System.Single m_MinWaterElevation`  
- `public System.Int32 m_XPReward`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

