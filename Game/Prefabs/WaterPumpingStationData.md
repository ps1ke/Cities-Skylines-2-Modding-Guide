# Game.Prefabs.WaterPumpingStationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.WaterPumpingStationData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterPumpingStationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.WaterPumpingStationData>, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.AllowedWaterTypes m_Types;
    public System.Int32 m_Capacity;
    public System.Single m_Purification;

    public System.Void Combine(Game.Prefabs.WaterPumpingStationData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.AllowedWaterTypes m_Types`  

```csharp
public Game.Prefabs.AllowedWaterTypes m_Types;
```

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Single m_Purification`  

```csharp
public System.Single m_Purification;
```


## Methods

- `public Combine(Game.Prefabs.WaterPumpingStationData otherData) : System.Void`  

```csharp
public void Combine(WaterPumpingStationData otherData)
	{
		m_Types |= otherData.m_Types;
		m_Capacity += otherData.m_Capacity;
		m_Purification = 1f - (1f - m_Purification) * (1f - otherData.m_Purification);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


