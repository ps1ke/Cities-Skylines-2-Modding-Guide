# Game.Prefabs.UpkeepModifierData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Game.Prefabs.ICombineBuffer<Game.Prefabs.UpkeepModifierData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct UpkeepModifierData : Unity.Entities.IBufferElementData, Game.Prefabs.ICombineBuffer<Game.Prefabs.UpkeepModifierData>, Colossal.Serialization.Entities.ISerializable
{
    public Game.Economy.Resource m_Resource;
    public System.Single m_Multiplier;

    public System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> result);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Single Transform(System.Single upkeep);
}
```


## Fields

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
```

- `public System.Single m_Multiplier`  

```csharp
public System.Single m_Multiplier;
```


## Methods

- `public Combine(Unity.Collections.NativeList<Game.Prefabs.UpkeepModifierData> result) : System.Void`  

```csharp
public void Combine(NativeList<UpkeepModifierData> result)
	{
		for (int i = 0; i < result.Length; i++)
		{
			ref UpkeepModifierData reference = ref result.ElementAt(i);
			if (reference.m_Resource == m_Resource)
			{
				reference.m_Multiplier *= m_Multiplier;
				return;
			}
		}
		result.Add(in this);
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

- `public Transform(System.Single upkeep) : System.Single`  

```csharp
public float Transform(float upkeep)
	{
		upkeep *= m_Multiplier;
		return upkeep;
	}
```


