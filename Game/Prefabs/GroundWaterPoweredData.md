# Game.Prefabs.GroundWaterPoweredData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.GroundWaterPoweredData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GroundWaterPoweredData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.GroundWaterPoweredData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Production;
    public System.Int32 m_MaximumGroundWater;

    public System.Void Combine(Game.Prefabs.GroundWaterPoweredData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Production`  

```csharp
public System.Int32 m_Production;
```

- `public System.Int32 m_MaximumGroundWater`  

```csharp
public System.Int32 m_MaximumGroundWater;
```


## Methods

- `public Combine(Game.Prefabs.GroundWaterPoweredData otherData) : System.Void`  

```csharp
public void Combine(GroundWaterPoweredData otherData)
	{
		m_Production += otherData.m_Production;
		m_MaximumGroundWater += otherData.m_MaximumGroundWater;
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


