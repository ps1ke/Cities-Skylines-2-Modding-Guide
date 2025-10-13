# Game.Vehicles.CargoTransport

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CargoTransport : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.CargoTransportFlags m_State;
    public System.UInt32 m_DepartureFrame;
    public System.Int32 m_RequestCount;
    public System.Single m_PathElementTime;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.CargoTransportFlags m_State`  

```csharp
public Game.Vehicles.CargoTransportFlags m_State;
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


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


