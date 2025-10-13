# Game.Prefabs.WorkplaceData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.WorkplaceData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WorkplaceData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.WorkplaceData>, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.WorkplaceComplexity m_Complexity;
    public System.Int32 m_MaxWorkers;
    public System.Single m_EveningShiftProbability;
    public System.Single m_NightShiftProbability;
    public System.Int32 m_MinimumWorkersLimit;

    public System.Void Combine(Game.Prefabs.WorkplaceData other);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.WorkplaceComplexity m_Complexity`  

```csharp
public Game.Prefabs.WorkplaceComplexity m_Complexity;
```

- `public System.Int32 m_MaxWorkers`  

```csharp
public System.Int32 m_MaxWorkers;
```

- `public System.Single m_EveningShiftProbability`  

```csharp
public System.Single m_EveningShiftProbability;
```

- `public System.Single m_NightShiftProbability`  

```csharp
public System.Single m_NightShiftProbability;
```

- `public System.Int32 m_MinimumWorkersLimit`  

```csharp
public System.Int32 m_MinimumWorkersLimit;
```


## Methods

- `public Combine(Game.Prefabs.WorkplaceData other) : System.Void`  

```csharp
public void Combine(WorkplaceData other)
	{
		int maxWorkers = m_MaxWorkers;
		m_MaxWorkers += other.m_MaxWorkers;
		m_MinimumWorkersLimit += m_MinimumWorkersLimit;
		m_EveningShiftProbability = math.lerp(other.m_EveningShiftProbability, m_EveningShiftProbability, maxWorkers / m_MaxWorkers);
		m_NightShiftProbability = math.lerp(other.m_NightShiftProbability, m_NightShiftProbability, maxWorkers / m_MaxWorkers);
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


