# Game.Prefabs.PostFacilityData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PostFacilityData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PostFacilityData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.PostFacilityData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_PostVanCapacity;
    public System.Int32 m_PostTruckCapacity;
    public System.Int32 m_MailCapacity;
    public System.Int32 m_SortingRate;

    public System.Void Combine(Game.Prefabs.PostFacilityData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_PostVanCapacity`  

```csharp
public System.Int32 m_PostVanCapacity;
```

- `public System.Int32 m_PostTruckCapacity`  

```csharp
public System.Int32 m_PostTruckCapacity;
```

- `public System.Int32 m_MailCapacity`  

```csharp
public System.Int32 m_MailCapacity;
```

- `public System.Int32 m_SortingRate`  

```csharp
public System.Int32 m_SortingRate;
```


## Methods

- `public Combine(Game.Prefabs.PostFacilityData otherData) : System.Void`  

```csharp
public void Combine(PostFacilityData otherData)
	{
		m_PostVanCapacity += otherData.m_PostVanCapacity;
		m_PostTruckCapacity += otherData.m_PostTruckCapacity;
		m_MailCapacity += otherData.m_MailCapacity;
		m_SortingRate += otherData.m_SortingRate;
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


