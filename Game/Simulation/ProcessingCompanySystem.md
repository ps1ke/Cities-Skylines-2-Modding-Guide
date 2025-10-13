# Game.Simulation.ProcessingCompanySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ProcessingCompanySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Collections.NativeArray<System.Int64> m_ProducedResources;
    private Unity.Jobs.JobHandle m_ProducedResourcesDeps;
    private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1038562630_0;
    public static const System.Int32 kMaxCommercialOutputResource;
    public static const System.Single kMaximumTransportUnitCost;

    public ProcessingCompanySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddProducedResourcesReader(Unity.Jobs.JobHandle handle);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int64> GetProducedResourcesArray(Unity.Jobs.JobHandle& dependencies);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem`  

```csharp
private Game.Simulation.ProductionSpecializationSystem m_ProductionSpecializationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Collections.NativeArray<System.Int64> m_ProducedResources`  

```csharp
private Unity.Collections.NativeArray<System.Int64> m_ProducedResources;
```

- `private Unity.Jobs.JobHandle m_ProducedResourcesDeps`  

```csharp
private Unity.Jobs.JobHandle m_ProducedResourcesDeps;
```

- `private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ProcessingCompanySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1038562630_0`  

```csharp
private Unity.Entities.EntityQuery __query_1038562630_0;
```

- `public static const System.Int32 kMaxCommercialOutputResource`  

```csharp
public static const System.Int32 kMaxCommercialOutputResource;
```

- `public static const System.Single kMaximumTransportUnitCost`  

```csharp
public static const System.Single kMaximumTransportUnitCost;
```


## Constructors

- `public ProcessingCompanySystem()`  

```csharp
public ProcessingCompanySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddProducedResourcesReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddProducedResourcesReader(Unity.Jobs.JobHandle handle);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetProducedResourcesArray(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeArray<System.Int64>`  

```csharp
public Unity.Collections.NativeArray<System.Int64> GetProducedResourcesArray(Unity.Jobs.JobHandle& dependencies);
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


## Nested types

- `Game.Simulation.ProcessingCompanySystem+UpdateProcessingJob`  
- `Game.Simulation.ProcessingCompanySystem+TypeHandle`  

