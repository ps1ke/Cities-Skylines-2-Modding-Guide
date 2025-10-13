# Game.Simulation.CountConsumptionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public class CountConsumptionSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Collections.NativeArray<System.Int32> m_Consumptions;
    private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator;
    private Unity.Jobs.JobHandle m_ReadDeps;
    private Unity.Jobs.JobHandle m_WriteDeps;
    private Unity.Jobs.JobHandle m_CopyDeps;
    public static readonly System.Int32 kUpdatesPerDay;

    public CountConsumptionSystem();

    public System.Void AddConsumptionReader(Unity.Jobs.JobHandle deps);
    public System.Void AddConsumptionWriter(Unity.Jobs.JobHandle deps);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetConsumptionAccumulator(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetConsumptions(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Int32> m_Consumptions`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Consumptions;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ConsumptionAccumulator;
```

- `private Unity.Jobs.JobHandle m_ReadDeps`  

```csharp
private Unity.Jobs.JobHandle m_ReadDeps;
```

- `private Unity.Jobs.JobHandle m_WriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_WriteDeps;
```

- `private Unity.Jobs.JobHandle m_CopyDeps`  

```csharp
private Unity.Jobs.JobHandle m_CopyDeps;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public CountConsumptionSystem()`  

```csharp
public CountConsumptionSystem();
```


## Methods

- `public AddConsumptionReader(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public System.Void AddConsumptionReader(Unity.Jobs.JobHandle deps);
```

- `public AddConsumptionWriter(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public System.Void AddConsumptionWriter(Unity.Jobs.JobHandle deps);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetConsumptionAccumulator(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetConsumptionAccumulator(Unity.Jobs.JobHandle& deps);
```

- `public GetConsumptions(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetConsumptions(Unity.Jobs.JobHandle& deps);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
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

- `Game.Simulation.CountConsumptionSystem+CopyConsumptionJob`  

