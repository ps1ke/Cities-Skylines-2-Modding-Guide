# Game.Prefabs.TrainEngineData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct TrainEngineData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Mathematics.int2 m_Count;

    public TrainEngineData(System.Int32 minCount, System.Int32 maxCount);

}
```


## Fields

- `public Unity.Mathematics.int2 m_Count`  

```csharp
public Unity.Mathematics.int2 m_Count;
```


## Constructors

- `public TrainEngineData(System.Int32 minCount, System.Int32 maxCount)`  

```csharp
public TrainEngineData(int minCount, int maxCount)
	{
		m_Count = new int2(minCount, maxCount);
	}
```


