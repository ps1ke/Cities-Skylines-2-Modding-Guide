# Game.Prefabs.TransportStopData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportStopData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ComfortFactor;
    public System.Single m_LoadingFactor;
    public System.Single m_AccessDistance;
    public System.Single m_BoardingTime;
    public Game.Prefabs.TransportType m_TransportType;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```

- `public System.Single m_LoadingFactor`  

```csharp
public System.Single m_LoadingFactor;
```

- `public System.Single m_AccessDistance`  

```csharp
public System.Single m_AccessDistance;
```

- `public System.Single m_BoardingTime`  

```csharp
public System.Single m_BoardingTime;
```

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
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


