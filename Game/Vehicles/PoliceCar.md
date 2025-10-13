# Game.Vehicles.PoliceCar

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PoliceCar : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.PoliceCarFlags m_State;
    public System.Int32 m_RequestCount;
    public System.Single m_PathElementTime;
    public System.UInt32 m_ShiftTime;
    public System.UInt32 m_EstimatedShift;
    public Game.Prefabs.PolicePurpose m_PurposeMask;

    public PoliceCar(Game.Vehicles.PoliceCarFlags flags, System.Int32 requestCount, Game.Prefabs.PolicePurpose purposeMask);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.PoliceCarFlags m_State`  

```csharp
public Game.Vehicles.PoliceCarFlags m_State;
```

- `public System.Int32 m_RequestCount`  

```csharp
public System.Int32 m_RequestCount;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```

- `public System.UInt32 m_ShiftTime`  

```csharp
public System.UInt32 m_ShiftTime;
```

- `public System.UInt32 m_EstimatedShift`  

```csharp
public System.UInt32 m_EstimatedShift;
```

- `public Game.Prefabs.PolicePurpose m_PurposeMask`  

```csharp
public Game.Prefabs.PolicePurpose m_PurposeMask;
```


## Constructors

- `public PoliceCar(Game.Vehicles.PoliceCarFlags flags, System.Int32 requestCount, Game.Prefabs.PolicePurpose purposeMask)`  

```csharp
public PoliceCar(Game.Vehicles.PoliceCarFlags flags, System.Int32 requestCount, Game.Prefabs.PolicePurpose purposeMask);
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


