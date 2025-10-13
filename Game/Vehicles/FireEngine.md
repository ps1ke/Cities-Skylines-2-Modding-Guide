# Game.Vehicles.FireEngine

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FireEngine : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.FireEngineFlags m_State;
    public System.Int32 m_RequestCount;
    public System.Single m_PathElementTime;
    public System.Single m_ExtinguishingAmount;
    public System.Single m_Efficiency;

    public FireEngine(Game.Vehicles.FireEngineFlags state, System.Int32 requestCount, System.Single extinguishingAmount, System.Single efficiency);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.FireEngineFlags m_State`  

```csharp
public Game.Vehicles.FireEngineFlags m_State;
```

- `public System.Int32 m_RequestCount`  

```csharp
public System.Int32 m_RequestCount;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```

- `public System.Single m_ExtinguishingAmount`  

```csharp
public System.Single m_ExtinguishingAmount;
```

- `public System.Single m_Efficiency`  

```csharp
public System.Single m_Efficiency;
```


## Constructors

- `public FireEngine(Game.Vehicles.FireEngineFlags state, System.Int32 requestCount, System.Single extinguishingAmount, System.Single efficiency)`  

```csharp
public FireEngine(FireEngineFlags state, int requestCount, float extinguishingAmount, float efficiency)
	{
		m_TargetRequest = Entity.Null;
		m_State = state;
		m_RequestCount = requestCount;
		m_PathElementTime = 0f;
		m_ExtinguishingAmount = extinguishingAmount;
		m_Efficiency = efficiency;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


