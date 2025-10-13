# Game.Achievements.EventAchievementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventAchievementTriggerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier;
    private Unity.Entities.EntityQuery m_TrackingQuery;
    private Unity.Entities.EntityQuery m_CreatedEventQuery;
    private Unity.Entities.EntityArchetype m_TrackingArchetype;
    private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle;

    public EventAchievementTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void StartTracking(Colossal.PSI.Common.AchievementId id, System.UInt32 startFrame, Unity.Entities.EntityCommandBuffer buffer);
    private System.Void StopTracking(Game.Achievements.EventAchievementTrackingData data, Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer buffer);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier;
```

- `private Unity.Entities.EntityQuery m_TrackingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrackingQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEventQuery;
```

- `private Unity.Entities.EntityArchetype m_TrackingArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TrackingArchetype;
```

- `private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventAchievementTriggerSystem()`  

```csharp
public EventAchievementTriggerSystem();
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

- `private StartTracking(Colossal.PSI.Common.AchievementId id, System.UInt32 startFrame, Unity.Entities.EntityCommandBuffer buffer) : System.Void`  

```csharp
private System.Void StartTracking(Colossal.PSI.Common.AchievementId id, System.UInt32 startFrame, Unity.Entities.EntityCommandBuffer buffer);
```

- `private StopTracking(Game.Achievements.EventAchievementTrackingData data, Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer buffer) : System.Void`  

```csharp
private System.Void StopTracking(Game.Achievements.EventAchievementTrackingData data, Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer buffer);
```


## Nested types

- `Game.Achievements.EventAchievementTriggerSystem+TypeHandle`  

