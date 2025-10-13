# Game.Vehicles.PublicTransport

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PublicTransport : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.PublicTransportFlags m_State;
    public System.UInt32 m_DepartureFrame;
    public System.Int32 m_RequestCount;
    public System.Single m_PathElementTime;
    public System.Single m_MaxBoardingDistance;
    public System.Single m_MinWaitingDistance;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.PublicTransportFlags m_State`  

```csharp
public Game.Vehicles.PublicTransportFlags m_State;
```

- `public System.UInt32 m_DepartureFrame`  

```csharp
public System.UInt32 m_DepartureFrame;
```

- `public System.Int32 m_RequestCount`  

```csharp
public System.Int32 m_RequestCount;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```

- `public System.Single m_MaxBoardingDistance`  

```csharp
public System.Single m_MaxBoardingDistance;
```

- `public System.Single m_MinWaitingDistance`  

```csharp
public System.Single m_MinWaitingDistance;
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


