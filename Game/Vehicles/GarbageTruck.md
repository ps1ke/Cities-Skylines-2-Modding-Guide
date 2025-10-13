# Game.Vehicles.GarbageTruck

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageTruck : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.GarbageTruckFlags m_State;
    public System.Int32 m_RequestCount;
    public System.Int32 m_Garbage;
    public System.Int32 m_EstimatedGarbage;
    public System.Single m_PathElementTime;

    public GarbageTruck(Game.Vehicles.GarbageTruckFlags flags, System.Int32 requestCount);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.GarbageTruckFlags m_State`  

```csharp
public Game.Vehicles.GarbageTruckFlags m_State;
```

- `public System.Int32 m_RequestCount`  

```csharp
public System.Int32 m_RequestCount;
```

- `public System.Int32 m_Garbage`  

```csharp
public System.Int32 m_Garbage;
```

- `public System.Int32 m_EstimatedGarbage`  

```csharp
public System.Int32 m_EstimatedGarbage;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```


## Constructors

- `public GarbageTruck(Game.Vehicles.GarbageTruckFlags flags, System.Int32 requestCount)`  

```csharp
public GarbageTruck(GarbageTruckFlags flags, int requestCount)
	{
		m_TargetRequest = Entity.Null;
		m_State = flags;
		m_RequestCount = requestCount;
		m_Garbage = 0;
		m_EstimatedGarbage = 0;
		m_PathElementTime = 0f;
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


