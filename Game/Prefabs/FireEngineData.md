# Game.Prefabs.FireEngineData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FireEngineData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ExtinguishingRate;
    public System.Single m_ExtinguishingSpread;
    public System.Single m_ExtinguishingCapacity;
    public System.Single m_DestroyedClearDuration;

    public FireEngineData(System.Single extinguishingRate, System.Single extinguishingSpread, System.Single extinguishingCapacity, System.Single destroyedClearDuration);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ExtinguishingRate`  

```csharp
public System.Single m_ExtinguishingRate;
```

- `public System.Single m_ExtinguishingSpread`  

```csharp
public System.Single m_ExtinguishingSpread;
```

- `public System.Single m_ExtinguishingCapacity`  

```csharp
public System.Single m_ExtinguishingCapacity;
```

- `public System.Single m_DestroyedClearDuration`  

```csharp
public System.Single m_DestroyedClearDuration;
```


## Constructors

- `public FireEngineData(System.Single extinguishingRate, System.Single extinguishingSpread, System.Single extinguishingCapacity, System.Single destroyedClearDuration)`  

```csharp
public FireEngineData(float extinguishingRate, float extinguishingSpread, float extinguishingCapacity, float destroyedClearDuration)
	{
		m_ExtinguishingRate = extinguishingRate;
		m_ExtinguishingSpread = extinguishingSpread;
		m_ExtinguishingCapacity = extinguishingCapacity;
		m_DestroyedClearDuration = destroyedClearDuration;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


