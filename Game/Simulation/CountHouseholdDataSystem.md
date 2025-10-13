# Game.Simulation.CountHouseholdDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountHouseholdDataSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies;
    private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies;
    private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData;
    private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData;
    private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData;
    private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed;
    private System.Boolean m_NeedForceCountData;
    private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation;
    private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle;

    public System.Int32 MovingInHouseholdCount { get; }
    public System.Int32 MovingInCitizenCount { get; }
    public System.Int32 MovingAwayHouseholdCount { get; }
    public System.Int32 CommuterHouseholdCount { get; }
    public System.Int32 TouristCitizenCount { get; }
    public System.Int32 HomelessHouseholdCount { get; }
    public System.Int32 HomelessCitizenCount { get; }
    public System.Int32 MovedInHouseholdCount { get; }
    public System.Int32 MovedInCitizenCount { get; }
    public System.Int32 ChildrenCount { get; }
    public System.Int32 AdultCount { get; }
    public System.Int32 TeenCount { get; }
    public System.Int32 SeniorCount { get; }
    public System.Int32 StudentCount { get; }
    public System.Int32 UneducatedCount { get; }
    public System.Int32 PoorlyEducatedCount { get; }
    public System.Int32 EducatedCount { get; }
    public System.Int32 WellEducatedCount { get; }
    public System.Int32 HighlyEducatedCount { get; }
    public System.Int32 WorkableCitizenCount { get; }
    public System.Int32 CityWorkerCount { get; }
    public System.Int32 DeadCitizenCount { get; }
    public System.Int32 AverageCitizenHappiness { get; }
    public System.Int32 AverageCitizenHealth { get; }
    public System.Single UnemploymentRate { get; }
    public System.Single HomelessnessRate { get; }

    public CountHouseholdDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddHouseholdDataReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetEmployables();
    public Game.Simulation.CountHouseholdDataSystem+HouseholdData GetHouseholdCountData();
    public Unity.Collections.NativeArray<System.Int32> GetResourceNeeds(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public System.Boolean IsCountDataNotReady();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies;
```

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData;
```

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData;
```

- `private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData`  

```csharp
private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed;
```

- `private System.Boolean m_NeedForceCountData`  

```csharp
private System.Boolean m_NeedForceCountData;
```

- `private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation;
```

- `private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 MovingInHouseholdCount { get }`  

```csharp
public System.Int32 MovingInHouseholdCount { get; }
```

- `public System.Int32 MovingInCitizenCount { get }`  

```csharp
public System.Int32 MovingInCitizenCount { get; }
```

- `public System.Int32 MovingAwayHouseholdCount { get }`  

```csharp
public System.Int32 MovingAwayHouseholdCount { get; }
```

- `public System.Int32 CommuterHouseholdCount { get }`  

```csharp
public System.Int32 CommuterHouseholdCount { get; }
```

- `public System.Int32 TouristCitizenCount { get }`  

```csharp
public System.Int32 TouristCitizenCount { get; }
```

- `public System.Int32 HomelessHouseholdCount { get }`  

```csharp
public System.Int32 HomelessHouseholdCount { get; }
```

- `public System.Int32 HomelessCitizenCount { get }`  

```csharp
public System.Int32 HomelessCitizenCount { get; }
```

- `public System.Int32 MovedInHouseholdCount { get }`  

```csharp
public System.Int32 MovedInHouseholdCount { get; }
```

- `public System.Int32 MovedInCitizenCount { get }`  

```csharp
public System.Int32 MovedInCitizenCount { get; }
```

- `public System.Int32 ChildrenCount { get }`  

```csharp
public System.Int32 ChildrenCount { get; }
```

- `public System.Int32 AdultCount { get }`  

```csharp
public System.Int32 AdultCount { get; }
```

- `public System.Int32 TeenCount { get }`  

```csharp
public System.Int32 TeenCount { get; }
```

- `public System.Int32 SeniorCount { get }`  

```csharp
public System.Int32 SeniorCount { get; }
```

- `public System.Int32 StudentCount { get }`  

```csharp
public System.Int32 StudentCount { get; }
```

- `public System.Int32 UneducatedCount { get }`  

```csharp
public System.Int32 UneducatedCount { get; }
```

- `public System.Int32 PoorlyEducatedCount { get }`  

```csharp
public System.Int32 PoorlyEducatedCount { get; }
```

- `public System.Int32 EducatedCount { get }`  

```csharp
public System.Int32 EducatedCount { get; }
```

- `public System.Int32 WellEducatedCount { get }`  

```csharp
public System.Int32 WellEducatedCount { get; }
```

- `public System.Int32 HighlyEducatedCount { get }`  

```csharp
public System.Int32 HighlyEducatedCount { get; }
```

- `public System.Int32 WorkableCitizenCount { get }`  

```csharp
public System.Int32 WorkableCitizenCount { get; }
```

- `public System.Int32 CityWorkerCount { get }`  

```csharp
public System.Int32 CityWorkerCount { get; }
```

- `public System.Int32 DeadCitizenCount { get }`  

```csharp
public System.Int32 DeadCitizenCount { get; }
```

- `public System.Int32 AverageCitizenHappiness { get }`  

```csharp
public System.Int32 AverageCitizenHappiness { get; }
```

- `public System.Int32 AverageCitizenHealth { get }`  

```csharp
public System.Int32 AverageCitizenHealth { get; }
```

- `public System.Single UnemploymentRate { get }`  

```csharp
public System.Single UnemploymentRate { get; }
```

- `public System.Single HomelessnessRate { get }`  

```csharp
public System.Single HomelessnessRate { get; }
```


## Constructors

- `public CountHouseholdDataSystem()`  

```csharp
public CountHouseholdDataSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddHouseholdDataReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public System.Void AddHouseholdDataReader(Unity.Jobs.JobHandle reader);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetEmployables() : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetEmployables();
```

- `public GetHouseholdCountData() : Game.Simulation.CountHouseholdDataSystem+HouseholdData`  

```csharp
public Game.Simulation.CountHouseholdDataSystem+HouseholdData GetHouseholdCountData();
```

- `public GetResourceNeeds(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> GetResourceNeeds(Unity.Jobs.JobHandle& deps);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public IsCountDataNotReady() : System.Boolean`  

```csharp
public System.Boolean IsCountDataNotReady();
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

- `Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData`  
- `Game.Simulation.CountHouseholdDataSystem+HouseholdData`  
- `Game.Simulation.CountHouseholdDataSystem+CountHouseholdJob`  
- `Game.Simulation.CountHouseholdDataSystem+ResultJob`  
- `Game.Simulation.CountHouseholdDataSystem+CitizenRequirementJob`  
- `Game.Simulation.CountHouseholdDataSystem+TypeHandle`  

