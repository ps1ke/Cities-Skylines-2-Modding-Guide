# Game.Vehicles.MaintenanceVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct MaintenanceVehicle : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.MaintenanceVehicleFlags m_State;
    public System.Int32 m_Maintained;
    public System.Int32 m_MaintainEstimate;
    public System.Int32 m_RequestCount;
    public System.Single m_PathElementTime;
    public System.Single m_Efficiency;

    public MaintenanceVehicle(Game.Vehicles.MaintenanceVehicleFlags flags, System.Int32 requestCount, System.Single efficiency);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.MaintenanceVehicleFlags m_State`  

```csharp
public Game.Vehicles.MaintenanceVehicleFlags m_State;
```

- `public System.Int32 m_Maintained`  

```csharp
public System.Int32 m_Maintained;
```

- `public System.Int32 m_MaintainEstimate`  

```csharp
public System.Int32 m_MaintainEstimate;
```

- `public System.Int32 m_RequestCount`  

```csharp
public System.Int32 m_RequestCount;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```

- `public System.Single m_Efficiency`  

```csharp
public System.Single m_Efficiency;
```


## Constructors

- `public MaintenanceVehicle(Game.Vehicles.MaintenanceVehicleFlags flags, System.Int32 requestCount, System.Single efficiency)`  

```csharp
public MaintenanceVehicle(Game.Vehicles.MaintenanceVehicleFlags flags, System.Int32 requestCount, System.Single efficiency);
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


