# Game.Simulation.ElectricityStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IElectricityStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityStatisticsSystem : Game.GameSystemBase, Game.Simulation.IElectricityStatisticsSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_ProducerGroup;
    private Unity.Entities.EntityQuery m_ConsumerGroup;
    private Unity.Entities.EntityQuery m_BatteryGroup;
    private Colossal.NativePerThreadSumInt m_Production;
    private Colossal.NativePerThreadSumInt m_Consumption;
    private Colossal.NativePerThreadSumInt m_FulfilledConsumption;
    private Colossal.NativePerThreadSumInt m_BatteryCharge;
    private Colossal.NativePerThreadSumInt m_BatteryCapacity;
    private System.Int32 m_LastProduction;
    private System.Int32 m_LastConsumption;
    private System.Int32 m_LastFulfilledConsumption;
    private System.Int32 m_LastBatteryCharge;
    private System.Int32 m_LastBatteryCapacity;
    private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle;

    public System.Int32 production { get; }
    public System.Int32 consumption { get; }
    public System.Int32 fulfilledConsumption { get; }
    public System.Int32 batteryCharge { get; }
    public System.Int32 batteryCapacity { get; }

    public ElectricityStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ProducerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ProducerGroup;
```

- `private Unity.Entities.EntityQuery m_ConsumerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerGroup;
```

- `private Unity.Entities.EntityQuery m_BatteryGroup`  

```csharp
private Unity.Entities.EntityQuery m_BatteryGroup;
```

- `private Colossal.NativePerThreadSumInt m_Production`  

```csharp
private Colossal.NativePerThreadSumInt m_Production;
```

- `private Colossal.NativePerThreadSumInt m_Consumption`  

```csharp
private Colossal.NativePerThreadSumInt m_Consumption;
```

- `private Colossal.NativePerThreadSumInt m_FulfilledConsumption`  

```csharp
private Colossal.NativePerThreadSumInt m_FulfilledConsumption;
```

- `private Colossal.NativePerThreadSumInt m_BatteryCharge`  

```csharp
private Colossal.NativePerThreadSumInt m_BatteryCharge;
```

- `private Colossal.NativePerThreadSumInt m_BatteryCapacity`  

```csharp
private Colossal.NativePerThreadSumInt m_BatteryCapacity;
```

- `private System.Int32 m_LastProduction`  

```csharp
private System.Int32 m_LastProduction;
```

- `private System.Int32 m_LastConsumption`  

```csharp
private System.Int32 m_LastConsumption;
```

- `private System.Int32 m_LastFulfilledConsumption`  

```csharp
private System.Int32 m_LastFulfilledConsumption;
```

- `private System.Int32 m_LastBatteryCharge`  

```csharp
private System.Int32 m_LastBatteryCharge;
```

- `private System.Int32 m_LastBatteryCapacity`  

```csharp
private System.Int32 m_LastBatteryCapacity;
```

- `private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ElectricityStatisticsSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 production { get }`  

```csharp
public System.Int32 production { get; }
```

- `public System.Int32 consumption { get }`  

```csharp
public System.Int32 consumption { get; }
```

- `public System.Int32 fulfilledConsumption { get }`  

```csharp
public System.Int32 fulfilledConsumption { get; }
```

- `public System.Int32 batteryCharge { get }`  

```csharp
public System.Int32 batteryCharge { get; }
```

- `public System.Int32 batteryCapacity { get }`  

```csharp
public System.Int32 batteryCapacity { get; }
```


## Constructors

- `public ElectricityStatisticsSystem()`  

```csharp
public ElectricityStatisticsSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.ElectricityStatisticsSystem+CountElectricityProductionJob`  
- `Game.Simulation.ElectricityStatisticsSystem+CountElectricityConsumptionJob`  
- `Game.Simulation.ElectricityStatisticsSystem+CountBatteryCapacityJob`  
- `Game.Simulation.ElectricityStatisticsSystem+TypeHandle`  

