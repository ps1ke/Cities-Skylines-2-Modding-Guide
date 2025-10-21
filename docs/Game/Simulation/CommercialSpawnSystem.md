# Game.Simulation.CommercialSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommercialSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup;
    private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame;
    private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle;

    public CommercialSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_CommercialCompanyPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_PropertyLessCompanyGroup;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame`  

```csharp
private Unity.Collections.NativeArray<System.UInt32> m_LastSpawnedCommercialFrame;
```

- `private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommercialSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CommercialSpawnSystem()`  

```csharp
public CommercialSpawnSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Simulation.CommercialSpawnSystem+SpawnCompanyJob`  
- `Game.Simulation.CommercialSpawnSystem+TypeHandle`  

