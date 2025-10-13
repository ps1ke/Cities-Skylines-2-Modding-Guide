# Game.Prefabs.TransportLineData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportLineData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_PathfindPrefab;
    public Game.Prefabs.TransportType m_TransportType;
    public System.Single m_DefaultVehicleInterval;
    public System.Single m_DefaultUnbunchingFactor;
    public System.Single m_StopDuration;
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;
    public Unity.Entities.Entity m_VehicleNotification;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_PathfindPrefab`  

```csharp
public Unity.Entities.Entity m_PathfindPrefab;
```

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Single m_DefaultVehicleInterval`  

```csharp
public System.Single m_DefaultVehicleInterval;
```

- `public System.Single m_DefaultUnbunchingFactor`  

```csharp
public System.Single m_DefaultUnbunchingFactor;
```

- `public System.Single m_StopDuration`  

```csharp
public System.Single m_StopDuration;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```

- `public Unity.Entities.Entity m_VehicleNotification`  

```csharp
public Unity.Entities.Entity m_VehicleNotification;
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


