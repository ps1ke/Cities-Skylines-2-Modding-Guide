# Game.Simulation.PollutionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionTriggerSystem : Game.GameSystemBase
{
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult;
    private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_380796347_0;

    public PollutionTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_AirPollutionResult;
```

- `private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PollutionTriggerSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_380796347_0`  

```csharp
private Unity.Entities.EntityQuery __query_380796347_0;
```


## Constructors

- `public PollutionTriggerSystem()`  

```csharp
public PollutionTriggerSystem();
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

- `Game.Simulation.PollutionTriggerSystem+CalculateAverageAirPollutionJob`  
- `Game.Simulation.PollutionTriggerSystem+SendPollutionTriggerJob`  
- `Game.Simulation.PollutionTriggerSystem+TypeHandle`  

