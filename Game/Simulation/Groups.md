# Game.Simulation.HumanNavigationSystem+Groups

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class Groups : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Game.Simulation.HumanNavigationSystem+Groups+TypeHandle __TypeHandle;

    public Groups();

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

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Game.Simulation.HumanNavigationSystem+Groups+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HumanNavigationSystem+Groups+TypeHandle __TypeHandle;
```


## Constructors

- `public Groups()`  

```csharp
public Groups();
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

- `Game.Simulation.HumanNavigationSystem+Groups+TypeHandle`  

