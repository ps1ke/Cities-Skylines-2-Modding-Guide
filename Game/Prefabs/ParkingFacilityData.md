# Game.Prefabs.ParkingFacilityData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.ParkingFacilityData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ParkingFacilityData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.ParkingFacilityData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ComfortFactor;
    public System.Int32 m_GarageMarkerCapacity;

    public System.Void Combine(Game.Prefabs.ParkingFacilityData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```

- `public System.Int32 m_GarageMarkerCapacity`  

```csharp
public System.Int32 m_GarageMarkerCapacity;
```


## Methods

- `public Combine(Game.Prefabs.ParkingFacilityData otherData) : System.Void`  

```csharp
public void Combine(ParkingFacilityData otherData)
	{
		m_ComfortFactor += otherData.m_ComfortFactor;
		m_GarageMarkerCapacity += otherData.m_GarageMarkerCapacity;
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


