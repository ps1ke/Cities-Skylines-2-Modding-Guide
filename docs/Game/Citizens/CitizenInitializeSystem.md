# Game.Citizens.CitizenInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NewCitizenQuery;
    private Unity.Entities.EntityQuery m_TimeSettingQuery;
    private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
    private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle;

    public CitizenInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NewCitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewCitizenQuery;
```

- `private Unity.Entities.EntityQuery m_TimeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Common.ModificationBarrier5 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
```

- `private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CitizenInitializeSystem()`  

```csharp
public CitizenInitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Citizens.CitizenInitializeSystem+InitializeCitizenJob`  
- `Game.Citizens.CitizenInitializeSystem+TypeHandle`  

