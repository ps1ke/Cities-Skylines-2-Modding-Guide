# Game.Simulation.TransportLineSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportLineSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_LineQuery;
    private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
    private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed;
    private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 UPDATE_INTERVAL;

    public TransportLineSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 CalculateVehicleCount(System.Single vehicleInterval, System.Single lineDuration);
    public static System.Single CalculateVehicleInterval(System.Single lineDuration, System.Int32 vehicleCount);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void GetMaxTransportSpeed(System.Single& maxPassengerTransportSpeed, System.Single& maxCargoTransportSpeed);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LineQuery`  

```csharp
private Unity.Entities.EntityQuery m_LineQuery;
```

- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_VehicleRequestArchetype;
```

- `private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_MaxTransportSpeed;
```

- `private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps`  

```csharp
private Unity.Jobs.JobHandle m_MaxTransportSpeedDeps;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportLineSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public TransportLineSystem()`  

```csharp
public TransportLineSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static CalculateVehicleCount(System.Single vehicleInterval, System.Single lineDuration) : System.Int32`  

```csharp
public static System.Int32 CalculateVehicleCount(System.Single vehicleInterval, System.Single lineDuration);
```

- `public static CalculateVehicleInterval(System.Single lineDuration, System.Int32 vehicleCount) : System.Single`  

```csharp
public static System.Single CalculateVehicleInterval(System.Single lineDuration, System.Int32 vehicleCount);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetMaxTransportSpeed(System.Single& maxPassengerTransportSpeed, System.Single& maxCargoTransportSpeed) : System.Void`  

```csharp
public System.Void GetMaxTransportSpeed(System.Single& maxPassengerTransportSpeed, System.Single& maxCargoTransportSpeed);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.TransportLineSystem+SortedVehicle`  
- `Game.Simulation.TransportLineSystem+VehicleAction`  
- `Game.Simulation.TransportLineSystem+VehicleActionType`  
- `Game.Simulation.TransportLineSystem+TransportLineTickJob`  
- `Game.Simulation.TransportLineSystem+VehicleActionJob`  
- `Game.Simulation.TransportLineSystem+TypeHandle`  

