# Game.Simulation.TransportVehicleRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportVehicleRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Route;
    public System.Single m_Priority;

    public TransportVehicleRequest(Unity.Entities.Entity route, System.Single priority);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Route`  

```csharp
public Unity.Entities.Entity m_Route;
```

- `public System.Single m_Priority`  

```csharp
public System.Single m_Priority;
```


## Constructors

- `public TransportVehicleRequest(Unity.Entities.Entity route, System.Single priority)`  

```csharp
public TransportVehicleRequest(Unity.Entities.Entity route, System.Single priority);
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


