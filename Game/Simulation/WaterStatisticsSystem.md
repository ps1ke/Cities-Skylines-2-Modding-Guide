# Game.Simulation.WaterStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IWaterStatisticsSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterStatisticsSystem : Game.GameSystemBase, Game.Simulation.IWaterStatisticsSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_PumpGroup;
    private Unity.Entities.EntityQuery m_OutletGroup;
    private Unity.Entities.EntityQuery m_ConsumerGroup;
    private Colossal.NativePerThreadSumInt m_FreshCapacity;
    private Colossal.NativePerThreadSumInt m_SewageCapacity;
    private Colossal.NativePerThreadSumInt m_Consumption;
    private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption;
    private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption;
    private System.Int32 m_LastFreshCapacity;
    private System.Int32 m_LastFreshConsumption;
    private System.Int32 m_LastFulfilledFreshConsumption;
    private System.Int32 m_LastSewageCapacity;
    private System.Int32 m_LastSewageConsumption;
    private System.Int32 m_LastFulfilledSewageConsumption;
    private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle;

    public System.Int32 freshCapacity { get; }
    public System.Int32 freshConsumption { get; }
    public System.Int32 fulfilledFreshConsumption { get; }
    public System.Int32 sewageCapacity { get; }
    public System.Int32 sewageConsumption { get; }
    public System.Int32 fulfilledSewageConsumption { get; }

    public WaterStatisticsSystem();

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

- `private Unity.Entities.EntityQuery m_PumpGroup`  

```csharp
private Unity.Entities.EntityQuery m_PumpGroup;
```

- `private Unity.Entities.EntityQuery m_OutletGroup`  

```csharp
private Unity.Entities.EntityQuery m_OutletGroup;
```

- `private Unity.Entities.EntityQuery m_ConsumerGroup`  

```csharp
private Unity.Entities.EntityQuery m_ConsumerGroup;
```

- `private Colossal.NativePerThreadSumInt m_FreshCapacity`  

```csharp
private Colossal.NativePerThreadSumInt m_FreshCapacity;
```

- `private Colossal.NativePerThreadSumInt m_SewageCapacity`  

```csharp
private Colossal.NativePerThreadSumInt m_SewageCapacity;
```

- `private Colossal.NativePerThreadSumInt m_Consumption`  

```csharp
private Colossal.NativePerThreadSumInt m_Consumption;
```

- `private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption`  

```csharp
private Colossal.NativePerThreadSumInt m_FulfilledFreshConsumption;
```

- `private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption`  

```csharp
private Colossal.NativePerThreadSumInt m_FulfilledSewageConsumption;
```

- `private System.Int32 m_LastFreshCapacity`  

```csharp
private System.Int32 m_LastFreshCapacity;
```

- `private System.Int32 m_LastFreshConsumption`  

```csharp
private System.Int32 m_LastFreshConsumption;
```

- `private System.Int32 m_LastFulfilledFreshConsumption`  

```csharp
private System.Int32 m_LastFulfilledFreshConsumption;
```

- `private System.Int32 m_LastSewageCapacity`  

```csharp
private System.Int32 m_LastSewageCapacity;
```

- `private System.Int32 m_LastSewageConsumption`  

```csharp
private System.Int32 m_LastSewageConsumption;
```

- `private System.Int32 m_LastFulfilledSewageConsumption`  

```csharp
private System.Int32 m_LastFulfilledSewageConsumption;
```

- `private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterStatisticsSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 freshCapacity { get }`  

```csharp
public System.Int32 freshCapacity { get; }
```

- `public System.Int32 freshConsumption { get }`  

```csharp
public System.Int32 freshConsumption { get; }
```

- `public System.Int32 fulfilledFreshConsumption { get }`  

```csharp
public System.Int32 fulfilledFreshConsumption { get; }
```

- `public System.Int32 sewageCapacity { get }`  

```csharp
public System.Int32 sewageCapacity { get; }
```

- `public System.Int32 sewageConsumption { get }`  

```csharp
public System.Int32 sewageConsumption { get; }
```

- `public System.Int32 fulfilledSewageConsumption { get }`  

```csharp
public System.Int32 fulfilledSewageConsumption { get; }
```


## Constructors

- `public WaterStatisticsSystem()`  

```csharp
public WaterStatisticsSystem();
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

- `Game.Simulation.WaterStatisticsSystem+CountPumpCapacityJob`  
- `Game.Simulation.WaterStatisticsSystem+CountOutletCapacityJob`  
- `Game.Simulation.WaterStatisticsSystem+CountWaterConsumptionJob`  
- `Game.Simulation.WaterStatisticsSystem+TypeHandle`  

