# Game.Prefabs.CargoTransportVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CargoTransportVehicleData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Economy.Resource m_Resources;
    public System.Int32 m_CargoCapacity;
    public System.Int32 m_MaxResourceCount;
    public System.Single m_MaintenanceRange;

    public CargoTransportVehicleData(Game.Economy.Resource resources, System.Int32 cargoCapacity, System.Int32 maxResourceCount, System.Single maintenanceRange);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Economy.Resource m_Resources`  

```csharp
public Game.Economy.Resource m_Resources;
```

- `public System.Int32 m_CargoCapacity`  

```csharp
public System.Int32 m_CargoCapacity;
```

- `public System.Int32 m_MaxResourceCount`  

```csharp
public System.Int32 m_MaxResourceCount;
```

- `public System.Single m_MaintenanceRange`  

```csharp
public System.Single m_MaintenanceRange;
```


## Constructors

- `public CargoTransportVehicleData(Game.Economy.Resource resources, System.Int32 cargoCapacity, System.Int32 maxResourceCount, System.Single maintenanceRange)`  

```csharp
public CargoTransportVehicleData(Resource resources, int cargoCapacity, int maxResourceCount, float maintenanceRange)
	{
		m_Resources = resources;
		m_CargoCapacity = cargoCapacity;
		m_MaxResourceCount = maxResourceCount;
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


