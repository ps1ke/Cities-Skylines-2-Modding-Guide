# Game.Simulation.CrimeStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CrimeStatisticsSystem : Game.GameSystemBase
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Game.Simulation.CrimeStatisticsSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_263205583_0;

    public CrimeStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Game.Simulation.CrimeStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CrimeStatisticsSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_263205583_0`  

```csharp
private Unity.Entities.EntityQuery __query_263205583_0;
```


## Constructors

- `public CrimeStatisticsSystem()`  

```csharp
public CrimeStatisticsSystem();
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

- `Game.Simulation.CrimeStatisticsSystem+AverageCrimeJob`  
- `Game.Simulation.CrimeStatisticsSystem+StatisticsJob`  
- `Game.Simulation.CrimeStatisticsSystem+TypeHandle`  

