# Game.Simulation.DeathCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeathCheckSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_DeathCheckQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityQuery m_TimeSettingsQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMaxAgeInGameYear;

    public DeathCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void PerformAfterDeathActions(Unity.Entities.Entity citizen, Unity.Entities.Entity household, Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> triggerBuffer, Unity.Collections.NativeQueue<Game.City.StatisticsEvent> statisticsEventQueue, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_DeathCheckQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathCheckQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMaxAgeInGameYear`  

```csharp
public static readonly System.Int32 kMaxAgeInGameYear;
```


## Constructors

- `public DeathCheckSystem()`  

```csharp
public DeathCheckSystem();
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

- `public static PerformAfterDeathActions(Unity.Entities.Entity citizen, Unity.Entities.Entity household, Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> triggerBuffer, Unity.Collections.NativeQueue<Game.City.StatisticsEvent> statisticsEventQueue, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens) : System.Void`  

```csharp
public static System.Void PerformAfterDeathActions(Unity.Entities.Entity citizen, Unity.Entities.Entity household, Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> triggerBuffer, Unity.Collections.NativeQueue<Game.City.StatisticsEvent> statisticsEventQueue, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens);
```


## Nested types

- `Game.Simulation.DeathCheckSystem+DeathCheckJob`  
- `Game.Simulation.DeathCheckSystem+TypeHandle`  

