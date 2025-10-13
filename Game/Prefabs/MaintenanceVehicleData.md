# Game.Prefabs.MaintenanceVehicleData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct MaintenanceVehicleData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Simulation.MaintenanceType m_MaintenanceType;
    public System.Int32 m_MaintenanceCapacity;
    public System.Int32 m_MaintenanceRate;

    public MaintenanceVehicleData(Game.Simulation.MaintenanceType maintenanceType, System.Int32 maintenanceCapacity, System.Int32 maintenanceRate);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Simulation.MaintenanceType m_MaintenanceType`  

```csharp
public Game.Simulation.MaintenanceType m_MaintenanceType;
```

- `public System.Int32 m_MaintenanceCapacity`  

```csharp
public System.Int32 m_MaintenanceCapacity;
```

- `public System.Int32 m_MaintenanceRate`  

```csharp
public System.Int32 m_MaintenanceRate;
```


## Constructors

- `public MaintenanceVehicleData(Game.Simulation.MaintenanceType maintenanceType, System.Int32 maintenanceCapacity, System.Int32 maintenanceRate)`  

```csharp
public MaintenanceVehicleData(MaintenanceType maintenanceType, int maintenanceCapacity, int maintenanceRate)
	{
		m_MaintenanceType = maintenanceType;
		m_MaintenanceCapacity = maintenanceCapacity;
		m_MaintenanceRate = maintenanceRate;
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


