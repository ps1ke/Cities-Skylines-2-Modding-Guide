# Game.Companies.StorageLimitData

**Assembly:** `Game`  
**Namespace:** `Game.Companies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Game.Prefabs.ICombineData<Game.Companies.StorageLimitData>`  

## Code

```csharp
public sealed struct StorageLimitData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, Game.Prefabs.ICombineData<Game.Companies.StorageLimitData>
{
    public System.Int32 m_Limit;

    public System.Void Combine(Game.Companies.StorageLimitData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetAdjustedLimitForWarehouse(Game.Prefabs.SpawnableBuildingData spawnable, Game.Prefabs.BuildingData building);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Limit`  

```csharp
public System.Int32 m_Limit;
```


## Methods

- `public Combine(Game.Companies.StorageLimitData otherData) : System.Void`  

```csharp
public void Combine(StorageLimitData otherData)
	{
		m_Limit += otherData.m_Limit;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetAdjustedLimitForWarehouse(Game.Prefabs.SpawnableBuildingData spawnable, Game.Prefabs.BuildingData building) : System.Int32`  

```csharp
public int GetAdjustedLimitForWarehouse(SpawnableBuildingData spawnable, BuildingData building)
	{
		return m_Limit * spawnable.m_Level * building.m_LotSize.x * building.m_LotSize.y;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


