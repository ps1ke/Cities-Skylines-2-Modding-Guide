# Game.Prefabs.DeathcareFacilityData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.DeathcareFacilityData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct DeathcareFacilityData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.DeathcareFacilityData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_HearseCapacity;
    public System.Int32 m_StorageCapacity;
    public System.Single m_ProcessingRate;
    public System.Boolean m_LongTermStorage;

    public System.Void Combine(Game.Prefabs.DeathcareFacilityData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_HearseCapacity`  

```csharp
public System.Int32 m_HearseCapacity;
```

- `public System.Int32 m_StorageCapacity`  

```csharp
public System.Int32 m_StorageCapacity;
```

- `public System.Single m_ProcessingRate`  

```csharp
public System.Single m_ProcessingRate;
```

- `public System.Boolean m_LongTermStorage`  

```csharp
public System.Boolean m_LongTermStorage;
```


## Methods

- `public Combine(Game.Prefabs.DeathcareFacilityData otherData) : System.Void`  

```csharp
public void Combine(DeathcareFacilityData otherData)
	{
		m_HearseCapacity += otherData.m_HearseCapacity;
		m_StorageCapacity += otherData.m_StorageCapacity;
		m_ProcessingRate += otherData.m_ProcessingRate;
		m_LongTermStorage |= otherData.m_LongTermStorage;
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


