# Game.Prefabs.SolarPoweredData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.SolarPoweredData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SolarPoweredData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.SolarPoweredData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Production;

    public System.Void Combine(Game.Prefabs.SolarPoweredData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Production`  

```csharp
public System.Int32 m_Production;
```


## Methods

- `public Combine(Game.Prefabs.SolarPoweredData otherData) : System.Void`  

```csharp
public void Combine(SolarPoweredData otherData)
	{
		m_Production += otherData.m_Production;
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


