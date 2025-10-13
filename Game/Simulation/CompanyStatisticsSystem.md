# Game.Simulation.CompanyStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyStatisticsSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CompanyStatisticsSystem+TypeHandle __TypeHandle;

    public CompanyStatisticsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CompanyStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CompanyStatisticsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompanyStatisticsSystem()`  

```csharp
public CompanyStatisticsSystem();
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

- `Game.Simulation.CompanyStatisticsSystem+ProcessCompanyStatisticsJob`  
- `Game.Simulation.CompanyStatisticsSystem+TypeHandle`  

