# Game.Simulation.WealthStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WealthStatisticsSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    protected Unity.Entities.EntityQuery m_HouseholdGroup;
    protected Unity.Entities.EntityQuery m_ServiceCompanyGroup;
    protected Unity.Entities.EntityQuery m_ProcessingCompanyGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.Simulation.WealthStatisticsSystem+TypeHandle __TypeHandle;

    public WealthStatisticsSystem();

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

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `protected Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
protected Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `protected Unity.Entities.EntityQuery m_ServiceCompanyGroup`  

```csharp
protected Unity.Entities.EntityQuery m_ServiceCompanyGroup;
```

- `protected Unity.Entities.EntityQuery m_ProcessingCompanyGroup`  

```csharp
protected Unity.Entities.EntityQuery m_ProcessingCompanyGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.Simulation.WealthStatisticsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WealthStatisticsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WealthStatisticsSystem()`  

```csharp
public WealthStatisticsSystem();
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

- `Game.Simulation.WealthStatisticsSystem+ResidentialWealthStatJob`  
- `Game.Simulation.WealthStatisticsSystem+ServiceWealthStatJob`  
- `Game.Simulation.WealthStatisticsSystem+ProcessingWealthStatJob`  
- `Game.Simulation.WealthStatisticsSystem+TypeHandle`  

