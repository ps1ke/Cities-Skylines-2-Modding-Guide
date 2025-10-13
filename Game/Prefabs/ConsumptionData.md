# Game.Prefabs.ConsumptionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.ConsumptionData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ConsumptionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.ConsumptionData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Upkeep;
    public System.Single m_ElectricityConsumption;
    public System.Single m_WaterConsumption;
    public System.Single m_GarbageAccumulation;
    public System.Single m_TelecomNeed;

    public System.Void AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void Combine(Game.Prefabs.ConsumptionData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Upkeep`  

```csharp
public System.Int32 m_Upkeep;
```

- `public System.Single m_ElectricityConsumption`  

```csharp
public System.Single m_ElectricityConsumption;
```

- `public System.Single m_WaterConsumption`  

```csharp
public System.Single m_WaterConsumption;
```

- `public System.Single m_GarbageAccumulation`  

```csharp
public System.Single m_GarbageAccumulation;
```

- `public System.Single m_TelecomNeed`  

```csharp
public System.Single m_TelecomNeed;
```


## Methods

- `public AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void AddArchetypeComponents(HashSet<ComponentType> components)
	{
		if (m_ElectricityConsumption > 0f)
		{
			components.Add(ComponentType.ReadWrite<ElectricityConsumer>());
		}
		if (m_WaterConsumption > 0f)
		{
			components.Add(ComponentType.ReadWrite<WaterConsumer>());
		}
		if (m_GarbageAccumulation > 0f)
		{
			components.Add(ComponentType.ReadWrite<GarbageProducer>());
		}
		if (m_TelecomNeed > 0f)
		{
			components.Add(ComponentType.ReadWrite<TelecomConsumer>());
		}
	}
```

- `public Combine(Game.Prefabs.ConsumptionData otherData) : System.Void`  

```csharp
public void Combine(ConsumptionData otherData)
	{
		m_Upkeep += otherData.m_Upkeep;
		m_ElectricityConsumption += otherData.m_ElectricityConsumption;
		m_WaterConsumption += otherData.m_WaterConsumption;
		m_GarbageAccumulation += otherData.m_GarbageAccumulation;
		m_TelecomNeed = math.max(m_TelecomNeed, otherData.m_TelecomNeed);
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


