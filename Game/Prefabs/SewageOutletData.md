# Game.Prefabs.SewageOutletData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.SewageOutletData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SewageOutletData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.SewageOutletData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Capacity;
    public System.Single m_Purification;

    public System.Void Combine(Game.Prefabs.SewageOutletData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Single m_Purification`  

```csharp
public System.Single m_Purification;
```


## Methods

- `public Combine(Game.Prefabs.SewageOutletData otherData) : System.Void`  

```csharp
public void Combine(SewageOutletData otherData)
	{
		m_Capacity += otherData.m_Capacity;
		m_Purification += otherData.m_Purification;
		m_Purification = math.min(1f, m_Purification);
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


