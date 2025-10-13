# Game.Simulation.PropertyProcessingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyProcessingSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_PropertyGroupQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Unity.Entities.EntityArchetype m_MovedEventArchetype;
    private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties;
    private Unity.Jobs.JobHandle m_Writers;
    private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle;

    public PropertyProcessingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle writer);
    public Unity.Collections.NativeQueue<Game.Buildings.RentAction> GetRentActionQueue(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PropertyGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_PropertyGroupQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_MovedEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MovedEventArchetype;
```

- `private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties;
```

- `private Unity.Jobs.JobHandle m_Writers`  

```csharp
private Unity.Jobs.JobHandle m_Writers;
```

- `private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PropertyProcessingSystem()`  

```csharp
public PropertyProcessingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public System.Void AddWriter(Unity.Jobs.JobHandle writer);
```

- `public GetRentActionQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Buildings.RentAction>`  

```csharp
public Unity.Collections.NativeQueue<Game.Buildings.RentAction> GetRentActionQueue(Unity.Jobs.JobHandle& deps);
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


## Nested types

- `Game.Simulation.PropertyProcessingSystem+PutPropertyOnMarketJob`  
- `Game.Simulation.PropertyProcessingSystem+PropertyRentJob`  
- `Game.Simulation.PropertyProcessingSystem+TypeHandle`  

