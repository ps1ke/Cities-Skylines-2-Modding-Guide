# Game.Prefabs.BatteryData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.BatteryData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct BatteryData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.BatteryData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Capacity;
    public System.Int32 m_PowerOutput;

    public System.Int64 capacityTicks { get; }

    public System.Void Combine(Game.Prefabs.BatteryData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Int32 m_PowerOutput`  

```csharp
public System.Int32 m_PowerOutput;
```


## Properties

- `public System.Int64 capacityTicks { get }`  

```csharp
public System.Int64 capacityTicks { get; }
```


## Methods

- `public Combine(Game.Prefabs.BatteryData otherData) : System.Void`  

```csharp
public void Combine(BatteryData otherData)
	{
		m_Capacity += otherData.m_Capacity;
		m_PowerOutput += otherData.m_PowerOutput;
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


