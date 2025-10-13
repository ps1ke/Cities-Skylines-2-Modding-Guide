# Game.Prefabs.PublicTransportVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PublicTransportVehicleData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.TransportType m_TransportType;
    public System.Int32 m_PassengerCapacity;
    public Game.Prefabs.PublicTransportPurpose m_PurposeMask;
    public System.Single m_MaintenanceRange;

    public PublicTransportVehicleData(Game.Prefabs.TransportType type, System.Int32 passengerCapacity, Game.Prefabs.PublicTransportPurpose purposeMask, System.Single maintenanceRange);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Int32 m_PassengerCapacity`  

```csharp
public System.Int32 m_PassengerCapacity;
```

- `public Game.Prefabs.PublicTransportPurpose m_PurposeMask`  

```csharp
public Game.Prefabs.PublicTransportPurpose m_PurposeMask;
```

- `public System.Single m_MaintenanceRange`  

```csharp
public System.Single m_MaintenanceRange;
```


## Constructors

- `public PublicTransportVehicleData(Game.Prefabs.TransportType type, System.Int32 passengerCapacity, Game.Prefabs.PublicTransportPurpose purposeMask, System.Single maintenanceRange)`  

```csharp
public PublicTransportVehicleData(TransportType type, int passengerCapacity, PublicTransportPurpose purposeMask, float maintenanceRange)
	{
		m_TransportType = type;
		m_PassengerCapacity = passengerCapacity;
		m_PurposeMask = purposeMask;
		m_MaintenanceRange = maintenanceRange;
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


