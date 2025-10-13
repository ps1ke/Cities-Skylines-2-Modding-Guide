# Game.Events.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_InstanceQuery;
    private Unity.Entities.EntityQuery m_DisasterConfigQuery;
    private Unity.Entities.EntityQuery m_TargetQuery;
    private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
    private Unity.Entities.EntityArchetype m_IgniteEventArchetype;
    private Unity.Entities.EntityArchetype m_ImpactEventArchetype;
    private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype;
    private Unity.Entities.EntityArchetype m_HealthEventArchetype;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Unity.Entities.EntityArchetype m_SpectateEventArchetype;
    private Unity.Entities.EntityArchetype m_CriminalEventArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
    private Game.Events.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddRandomTarget(Unity.Entities.DynamicBuffer<Game.Events.TargetElement> targets, Game.Prefabs.EventTargetType targetType, Game.Prefabs.TransportType transportType);
    private System.Int32 CountInstances(Unity.Entities.Entity prefab);
    private Unity.Mathematics.float3 FindRandomLocation(Unity.Mathematics.Random& random);
    private Unity.Entities.EntityCommandBuffer GetCommandBuffer();
    private System.Void InitializeCalendarEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeCrimeEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeDestruction(Unity.Entities.Entity eventEntity);
    private System.Void InitializeFire(Unity.Entities.Entity eventEntity);
    private System.Void InitializeHealthEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeMeetingEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeSpectatorEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeTrafficAccident(Unity.Entities.Entity eventEntity);
    private System.Void InitializeWaterLevelChangeEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeWeatherEvent(Unity.Entities.Entity eventEntity);
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

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_InstanceQuery`  

```csharp
private Unity.Entities.EntityQuery m_InstanceQuery;
```

- `private Unity.Entities.EntityQuery m_DisasterConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_DisasterConfigQuery;
```

- `private Unity.Entities.EntityQuery m_TargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_TargetQuery;
```

- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
```

- `private Unity.Entities.EntityArchetype m_IgniteEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_IgniteEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_ImpactEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ImpactEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_HealthEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HealthEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_SpectateEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_SpectateEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_CriminalEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_CriminalEventArchetype;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```

- `private Game.Events.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.InitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSystem()`  

```csharp
public InitializeSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddRandomTarget(Unity.Entities.DynamicBuffer<Game.Events.TargetElement> targets, Game.Prefabs.EventTargetType targetType, Game.Prefabs.TransportType transportType) : System.Void`  

```csharp
private System.Void AddRandomTarget(Unity.Entities.DynamicBuffer<Game.Events.TargetElement> targets, Game.Prefabs.EventTargetType targetType, Game.Prefabs.TransportType transportType);
```

- `private CountInstances(Unity.Entities.Entity prefab) : System.Int32`  

```csharp
private System.Int32 CountInstances(Unity.Entities.Entity prefab);
```

- `private FindRandomLocation(Unity.Mathematics.Random& random) : Unity.Mathematics.float3`  

```csharp
private Unity.Mathematics.float3 FindRandomLocation(Unity.Mathematics.Random& random);
```

- `private GetCommandBuffer() : Unity.Entities.EntityCommandBuffer`  

```csharp
private Unity.Entities.EntityCommandBuffer GetCommandBuffer();
```

- `private InitializeCalendarEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeCalendarEvent(Unity.Entities.Entity eventEntity);
```

- `private InitializeCrimeEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeCrimeEvent(Unity.Entities.Entity eventEntity);
```

- `private InitializeDestruction(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeDestruction(Unity.Entities.Entity eventEntity);
```

- `private InitializeFire(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeFire(Unity.Entities.Entity eventEntity);
```

- `private InitializeHealthEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeHealthEvent(Unity.Entities.Entity eventEntity);
```

- `private InitializeMeetingEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeMeetingEvent(Unity.Entities.Entity eventEntity);
```

- `private InitializeSpectatorEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeSpectatorEvent(Unity.Entities.Entity eventEntity);
```

- `private InitializeTrafficAccident(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeTrafficAccident(Unity.Entities.Entity eventEntity);
```

- `private InitializeWaterLevelChangeEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeWaterLevelChangeEvent(Unity.Entities.Entity eventEntity);
```

- `private InitializeWeatherEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private System.Void InitializeWeatherEvent(Unity.Entities.Entity eventEntity);
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

- `Game.Events.InitializeSystem+RandomEventTargetJob`  
- `Game.Events.InitializeSystem+TypeHandle`  

