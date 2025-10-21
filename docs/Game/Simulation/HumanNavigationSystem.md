# Game.Simulation.HumanNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HumanNavigationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.HumanNavigationSystem+Actions m_Actions;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Game.Simulation.HumanNavigationSystem+TypeHandle __TypeHandle;

    public HumanNavigationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.HumanNavigationSystem+Actions m_Actions`  

```csharp
private Game.Simulation.HumanNavigationSystem+Actions m_Actions;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Game.Simulation.HumanNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HumanNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HumanNavigationSystem()`  

```csharp
public HumanNavigationSystem();
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

- `Game.Simulation.HumanNavigationSystem+Groups`  
- `Game.Simulation.HumanNavigationSystem+Actions`  
- `Game.Simulation.HumanNavigationSystem+GroupNavigationJob`  
- `Game.Simulation.HumanNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.HumanNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.HumanNavigationSystem+TypeHandle`  

