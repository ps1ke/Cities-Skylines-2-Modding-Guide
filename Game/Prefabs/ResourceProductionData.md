# Game.Prefabs.ResourceProductionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ResourceProductionData : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.Economy.Resource m_Type;
    public System.Int32 m_ProductionRate;
    public System.Int32 m_StorageCapacity;

    public ResourceProductionData(Game.Economy.Resource type, System.Int32 productionRate, System.Int32 storageCapacity);

    public static System.Void Combine(Unity.Collections.NativeList<Game.Prefabs.ResourceProductionData> resources, Unity.Entities.DynamicBuffer<Game.Prefabs.ResourceProductionData> others);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Economy.Resource m_Type`  

```csharp
public Game.Economy.Resource m_Type;
```

- `public System.Int32 m_ProductionRate`  

```csharp
public System.Int32 m_ProductionRate;
```

- `public System.Int32 m_StorageCapacity`  

```csharp
public System.Int32 m_StorageCapacity;
```


## Constructors

- `public ResourceProductionData(Game.Economy.Resource type, System.Int32 productionRate, System.Int32 storageCapacity)`  

```csharp
public ResourceProductionData(Resource type, int productionRate, int storageCapacity)
	{
		m_Type = type;
		m_ProductionRate = productionRate;
		m_StorageCapacity = storageCapacity;
	}
```


## Methods

- `public static Combine(Unity.Collections.NativeList<Game.Prefabs.ResourceProductionData> resources, Unity.Entities.DynamicBuffer<Game.Prefabs.ResourceProductionData> others) : System.Void`  

```csharp
public static void Combine(NativeList<ResourceProductionData> resources, DynamicBuffer<ResourceProductionData> others)
	{
		for (int i = 0; i < others.Length; i++)
		{
			ResourceProductionData value = others[i];
			int num = 0;
			while (true)
			{
				if (num < resources.Length)
				{
					ResourceProductionData value2 = resources[num];
					if (value2.m_Type == value.m_Type)
					{
						value2.m_ProductionRate += value.m_ProductionRate;
						value2.m_StorageCapacity += value.m_StorageCapacity;
						resources[num] = value2;
						break;
					}
					num++;
					continue;
				}
				resources.Add(in value);
				break;
			}
		}
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


