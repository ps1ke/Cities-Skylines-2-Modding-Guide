# Game.Prefabs.TelecomFacilityData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.TelecomFacilityData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TelecomFacilityData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.TelecomFacilityData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Range;
    public System.Single m_NetworkCapacity;
    public System.Boolean m_PenetrateTerrain;

    public System.Void Combine(Game.Prefabs.TelecomFacilityData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Range`  

```csharp
public System.Single m_Range;
```

- `public System.Single m_NetworkCapacity`  

```csharp
public System.Single m_NetworkCapacity;
```

- `public System.Boolean m_PenetrateTerrain`  

```csharp
public System.Boolean m_PenetrateTerrain;
```


## Methods

- `public Combine(Game.Prefabs.TelecomFacilityData otherData) : System.Void`  

```csharp
public void Combine(TelecomFacilityData otherData)
	{
		m_Range += otherData.m_Range;
		m_NetworkCapacity += otherData.m_NetworkCapacity;
		m_PenetrateTerrain |= otherData.m_PenetrateTerrain;
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


