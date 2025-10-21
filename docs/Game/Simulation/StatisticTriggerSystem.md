# Game.Simulation.StatisticTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StatisticTriggerSystem : Game.GameSystemBase
{
    private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdatesPerDay;

    public StatisticTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StatisticTriggerSystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public StatisticTriggerSystem()`  

```csharp
public StatisticTriggerSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.StatisticTriggerSystem+SendTriggersJob`  
- `Game.Simulation.StatisticTriggerSystem+TypeHandle`  

