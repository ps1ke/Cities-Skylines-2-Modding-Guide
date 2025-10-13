# Game.Prefabs.MaintenanceDepotData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.MaintenanceDepotData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct MaintenanceDepotData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.MaintenanceDepotData>, Colossal.Serialization.Entities.ISerializable
{
    public Game.Simulation.MaintenanceType m_MaintenanceType;
    public System.Int32 m_VehicleCapacity;
    public System.Single m_VehicleEfficiency;

    public System.Void Combine(Game.Prefabs.MaintenanceDepotData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Simulation.MaintenanceType m_MaintenanceType`  

```csharp
public Game.Simulation.MaintenanceType m_MaintenanceType;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Single m_VehicleEfficiency`  

```csharp
public System.Single m_VehicleEfficiency;
```


## Methods

- `public Combine(Game.Prefabs.MaintenanceDepotData otherData) : System.Void`  

```csharp
public void Combine(MaintenanceDepotData otherData)
	{
		m_MaintenanceType |= otherData.m_MaintenanceType;
		m_VehicleCapacity += otherData.m_VehicleCapacity;
		m_VehicleEfficiency += otherData.m_VehicleEfficiency;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


