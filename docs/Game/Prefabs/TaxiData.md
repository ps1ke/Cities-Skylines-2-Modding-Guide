# Game.Prefabs.TaxiData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TaxiData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_PassengerCapacity;
    public System.Single m_MaintenanceRange;

    public TaxiData(System.Int32 passengerCapacity, System.Single maintenanceRange);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_PassengerCapacity`  

```csharp
public System.Int32 m_PassengerCapacity;
```

- `public System.Single m_MaintenanceRange`  

```csharp
public System.Single m_MaintenanceRange;
```


## Constructors

- `public TaxiData(System.Int32 passengerCapacity, System.Single maintenanceRange)`  

```csharp
public TaxiData(System.Int32 passengerCapacity, System.Single maintenanceRange);
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


