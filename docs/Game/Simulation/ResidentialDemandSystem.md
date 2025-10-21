# Game.Simulation.ResidentialDemandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResidentialDemandSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityQuery m_DemandParameterGroup;
    private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand;
    private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand;
    private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors;
    private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Int32 m_LastHouseholdDemand;
    private Unity.Mathematics.int3 m_LastBuildingDemand;
    private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
    private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kMaxFactorEffect;

    public System.Int32 householdDemand { get; }
    public Unity.Mathematics.int3 buildingDemand { get; }

    public ResidentialDemandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetHighDensityDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetLowDensityDemandFactors(Unity.Jobs.JobHandle& deps);
    public Unity.Collections.NativeArray<System.Int32> GetMediumDensityDemandFactors(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem`  

```csharp
private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  

```csharp
private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityQuery m_DemandParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterGroup;
```

- `private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedZonePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_HouseholdDemand;
```

- `private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand`  

```csharp
private Colossal.Collections.NativeValue<Unity.Mathematics.int3> m_BuildingDemand;
```

- `private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_LowDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_MediumDemandFactors;
```

- `private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_HighDemandFactors;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Int32 m_LastHouseholdDemand`  

```csharp
private System.Int32 m_LastHouseholdDemand;
```

- `private Unity.Mathematics.int3 m_LastBuildingDemand`  

```csharp
private Unity.Mathematics.int3 m_LastBuildingDemand;
```

- `private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector`  

```csharp
private Unity.Mathematics.float2 m_ResidentialDemandWeightsSelector;
```

- `private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResidentialDemandSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kMaxFactorEffect`  

```csharp
public static readonly System.Int32 kMaxFactorEffect;
```


## Properties

- `public System.Int32 householdDemand { get }`  

```csharp
public System.Int32 householdDemand { get; }
```

- `public Unity.Mathematics.int3 buildingDemand { get }`  

```csharp
public Unity.Mathematics.int3 buildingDemand { get; }
```


## Constructors

- `public ResidentialDemandSystem()`  

```csharp
public ResidentialDemandSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public System.Void AddReader(Unity.Jobs.JobHandle reader);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetHighDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetHighDensityDemandFactors(Unity.Jobs.JobHandle& deps);
```

- `public GetLowDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetLowDensityDemandFactors(Unity.Jobs.JobHandle& deps);
```

- `public GetMediumDensityDemandFactors(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetMediumDensityDemandFactors(Unity.Jobs.JobHandle& deps);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
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

- `Game.Simulation.ResidentialDemandSystem+UpdateResidentialDemandJob`  
- `Game.Simulation.ResidentialDemandSystem+TypeHandle`  

