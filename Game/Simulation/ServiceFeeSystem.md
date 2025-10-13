# Game.Simulation.ServiceFeeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Simulation.IServiceFeeSystem`, `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceFeeSystem : Game.GameSystemBase, Game.Simulation.IServiceFeeSystem, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FeeCollectorGroup;
    private Unity.Entities.EntityQuery m_CollectedFeeGroup;
    private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue;
    private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees;
    private Unity.Jobs.JobHandle m_Writers;
    private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdatesPerDay;

    public ServiceFeeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle deps);
    private System.Void CacheFees(System.Boolean reset);
    public System.Void Deserialize<TReader>(TReader reader);
    public static System.Single GetConsumptionMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
    public static Game.City.PlayerResource GetEducationResource(System.Int32 level);
    public static System.Single GetEfficiencyMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
    public static System.Single GetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees);
    public Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> GetFeeQueue(Unity.Jobs.JobHandle& deps);
    public static System.Int32 GetHappinessEffect(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& happinessParameters);
    public System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee);
    public static System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees);
    public Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> GetServiceFees();
    public Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource);
    public static Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public static System.Void SetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single value);
    public static System.Boolean TryGetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single& fee);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FeeCollectorGroup`  

```csharp
private Unity.Entities.EntityQuery m_FeeCollectorGroup;
```

- `private Unity.Entities.EntityQuery m_CollectedFeeGroup`  

```csharp
private Unity.Entities.EntityQuery m_CollectedFeeGroup;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> m_FeeQueue;
```

- `private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> m_CityServiceFees;
```

- `private Unity.Jobs.JobHandle m_Writers`  

```csharp
private Unity.Jobs.JobHandle m_Writers;
```

- `private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceFeeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public ServiceFeeSystem()`  

```csharp
public ServiceFeeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddQueueWriter(Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
public System.Void AddQueueWriter(Unity.Jobs.JobHandle deps);
```

- `private CacheFees(System.Boolean reset = False) : System.Void`  

```csharp
private System.Void CacheFees(System.Boolean reset);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static GetConsumptionMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters) : System.Single`  

```csharp
public static System.Single GetConsumptionMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.ServiceFeeParameterData& feeParameters);
```

- `public static GetEducationResource(System.Int32 level) : Game.City.PlayerResource`  

```csharp
public static Game.City.PlayerResource GetEducationResource(System.Int32 level);
```

- `public static GetEfficiencyMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters) : System.Single`  

```csharp
public static System.Single GetEfficiencyMultiplier(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.BuildingEfficiencyParameterData& efficiencyParameters);
```

- `public static GetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees) : System.Single`  

```csharp
public static System.Single GetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees);
```

- `public GetFeeQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent>`  

```csharp
public Unity.Collections.NativeQueue<Game.Simulation.ServiceFeeSystem+FeeEvent> GetFeeQueue(Unity.Jobs.JobHandle& deps);
```

- `public static GetHappinessEffect(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& happinessParameters) : System.Int32`  

```csharp
public static System.Int32 GetHappinessEffect(Game.City.PlayerResource resource, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& happinessParameters);
```

- `public GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee) : System.Int32`  

```csharp
public System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee);
```

- `public static GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees) : System.Int32`  

```csharp
public static System.Int32 GetServiceFeeIncomeEstimate(Game.City.PlayerResource resource, System.Single fee, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees);
```

- `public GetServiceFees() : Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData>`  

```csharp
public Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> GetServiceFees();
```

- `public GetServiceFees(Game.City.PlayerResource resource) : Unity.Mathematics.int3`  

```csharp
public Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource);
```

- `public static GetServiceFees(Game.City.PlayerResource resource, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees) : Unity.Mathematics.int3`  

```csharp
public static Unity.Mathematics.int3 GetServiceFees(Game.City.PlayerResource resource, Unity.Collections.NativeList<Game.Simulation.CollectedCityServiceFeeData> fees);
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public static SetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single value) : System.Void`  

```csharp
public static System.Void SetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single value);
```

- `public static TryGetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single& fee) : System.Boolean`  

```csharp
public static System.Boolean TryGetFee(Game.City.PlayerResource resource, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees, System.Single& fee);
```


## Nested types

- `Game.Simulation.ServiceFeeSystem+FeeEvent`  
- `Game.Simulation.ServiceFeeSystem+PayFeeJob`  
- `Game.Simulation.ServiceFeeSystem+FeeToCityJob`  
- `Game.Simulation.ServiceFeeSystem+TriggerJob`  
- `Game.Simulation.ServiceFeeSystem+TypeHandle`  

