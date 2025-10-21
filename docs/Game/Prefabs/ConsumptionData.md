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
public System.Void AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public Combine(Game.Prefabs.ConsumptionData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.ConsumptionData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


