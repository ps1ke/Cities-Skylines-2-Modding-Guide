# Game.Simulation.FireSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireSimulationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Objects.SearchSystem m_SearchSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.FireHazardSystem m_FireHazardSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_FireQuery;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Unity.Entities.EntityArchetype m_IgniteEventArchetype;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
    private Game.Simulation.FireSimulationSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public FireSimulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Objects.SearchSystem m_SearchSystem`  

```csharp
private Game.Objects.SearchSystem m_SearchSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  

```csharp
private Game.Simulation.FireHazardSystem m_FireHazardSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_FireQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_IgniteEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_IgniteEventArchetype;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  

```csharp
private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData;
```

- `private Game.Simulation.FireSimulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FireSimulationSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public FireSimulationSystem()`  

```csharp
public FireSimulationSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.FireSimulationSystem+FireSimulationJob`  
- `Game.Simulation.FireSimulationSystem+FireSpreadCheckJob`  
- `Game.Simulation.FireSimulationSystem+TypeHandle`  

