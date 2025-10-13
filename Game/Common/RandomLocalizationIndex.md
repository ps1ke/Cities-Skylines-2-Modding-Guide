# Game.Common.RandomLocalizationIndex

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct RandomLocalizationIndex : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Index;
    public static readonly Game.Common.RandomLocalizationIndex kNone;

    public RandomLocalizationIndex(System.Int32 index);

    public System.Void Deserialize<TReader>(TReader reader);
    public static System.Void EnsureValidRandomIndices(Unity.Entities.DynamicBuffer<Game.Common.RandomLocalizationIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalizationCount> counts, Unity.Mathematics.Random& random);
    public static System.Void GenerateRandomIndices(Unity.Entities.DynamicBuffer<Game.Common.RandomLocalizationIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalizationCount> counts, Unity.Mathematics.Random& random);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```

- `public static readonly Game.Common.RandomLocalizationIndex kNone`  

```csharp
public static readonly Game.Common.RandomLocalizationIndex kNone;
```


## Constructors

- `public RandomLocalizationIndex(System.Int32 index)`  

```csharp
public RandomLocalizationIndex(int index)
	{
		m_Index = index;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static EnsureValidRandomIndices(Unity.Entities.DynamicBuffer<Game.Common.RandomLocalizationIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalizationCount> counts, Unity.Mathematics.Random& random) : System.Void`  

```csharp
public static void EnsureValidRandomIndices(DynamicBuffer<RandomLocalizationIndex> indices, DynamicBuffer<LocalizationCount> counts, ref Random random)
	{
		if (indices.Length == counts.Length)
		{
			for (int i = 0; i < counts.Length; i++)
			{
				int count = counts[i].m_Count;
				if (indices[i].m_Index < 0 || indices[i].m_Index >= count)
				{
					indices[i] = new RandomLocalizationIndex((count > 0) ? random.NextInt(count) : (-1));
				}
			}
		}
		else
		{
			GenerateRandomIndices(indices, counts, ref random);
		}
	}
```

- `public static GenerateRandomIndices(Unity.Entities.DynamicBuffer<Game.Common.RandomLocalizationIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.LocalizationCount> counts, Unity.Mathematics.Random& random) : System.Void`  

```csharp
public static void GenerateRandomIndices(DynamicBuffer<RandomLocalizationIndex> indices, DynamicBuffer<LocalizationCount> counts, ref Random random)
	{
		indices.ResizeUninitialized(counts.Length);
		for (int i = 0; i < counts.Length; i++)
		{
			int count = counts[i].m_Count;
			indices[i] = new RandomLocalizationIndex((count > 0) ? random.NextInt(count) : (-1));
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


