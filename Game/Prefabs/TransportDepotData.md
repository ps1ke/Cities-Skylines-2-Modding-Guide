# Game.Prefabs.TransportDepotData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.TransportDepotData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportDepotData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.TransportDepotData>, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Vehicles.EnergyTypes m_EnergyTypes;
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Boolean m_DispatchCenter;
    public System.Int32 m_VehicleCapacity;
    public System.Single m_ProductionDuration;
    public System.Single m_MaintenanceDuration;

    public System.Void Combine(Game.Prefabs.TransportDepotData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyTypes;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Boolean m_DispatchCenter`  

```csharp
public System.Boolean m_DispatchCenter;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```

- `public System.Single m_ProductionDuration`  

```csharp
public System.Single m_ProductionDuration;
```

- `public System.Single m_MaintenanceDuration`  

```csharp
public System.Single m_MaintenanceDuration;
```


## Methods

- `public Combine(Game.Prefabs.TransportDepotData otherData) : System.Void`  

```csharp
public void Combine(TransportDepotData otherData)
	{
		m_EnergyTypes |= otherData.m_EnergyTypes;
		m_DispatchCenter |= otherData.m_DispatchCenter;
		m_VehicleCapacity += otherData.m_VehicleCapacity;
		m_ProductionDuration += otherData.m_ProductionDuration;
		m_MaintenanceDuration += otherData.m_MaintenanceDuration;
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


