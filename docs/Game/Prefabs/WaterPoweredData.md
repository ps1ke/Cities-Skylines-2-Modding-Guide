# Game.Prefabs.WaterPoweredData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.WaterPoweredData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterPoweredData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.WaterPoweredData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ProductionFactor;
    public System.Single m_CapacityFactor;

    public System.Void Combine(Game.Prefabs.WaterPoweredData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ProductionFactor`  

```csharp
public System.Single m_ProductionFactor;
```

- `public System.Single m_CapacityFactor`  

```csharp
public System.Single m_CapacityFactor;
```


## Methods

- `public Combine(Game.Prefabs.WaterPoweredData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.WaterPoweredData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


