# Game.Prefabs.WindPoweredData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.WindPoweredData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WindPoweredData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.WindPoweredData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_MaximumWind;
    public System.Int32 m_Production;

    public System.Void Combine(Game.Prefabs.WindPoweredData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_MaximumWind`  

```csharp
public System.Single m_MaximumWind;
```

- `public System.Int32 m_Production`  

```csharp
public System.Int32 m_Production;
```


## Methods

- `public Combine(Game.Prefabs.WindPoweredData otherData) : System.Void`  

```csharp
public void Combine(WindPoweredData otherData)
	{
		if (m_Production > 0)
		{
			m_MaximumWind = math.min(m_MaximumWind, otherData.m_MaximumWind);
		}
		else
		{
			m_MaximumWind = otherData.m_MaximumWind;
		}
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


