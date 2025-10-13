# Game.Prefabs.GarbagePoweredData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.GarbagePoweredData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbagePoweredData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.GarbagePoweredData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Capacity;
    public System.Single m_ProductionPerUnit;

    public System.Void Combine(Game.Prefabs.GarbagePoweredData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Single m_ProductionPerUnit`  

```csharp
public System.Single m_ProductionPerUnit;
```


## Methods

- `public Combine(Game.Prefabs.GarbagePoweredData otherData) : System.Void`  

```csharp
public void Combine(GarbagePoweredData otherData)
	{
		m_Capacity += otherData.m_Capacity;
		m_ProductionPerUnit = math.max(m_ProductionPerUnit, otherData.m_ProductionPerUnit);
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


