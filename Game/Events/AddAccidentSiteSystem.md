# Game.Events.AddAccidentSiteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AddAccidentSiteSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ImpactQuery;
    private Game.Events.AddAccidentSiteSystem+TypeHandle __TypeHandle;

    public AddAccidentSiteSystem();

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

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ImpactQuery`  

```csharp
private Unity.Entities.EntityQuery m_ImpactQuery;
```

- `private Game.Events.AddAccidentSiteSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.AddAccidentSiteSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AddAccidentSiteSystem()`  

```csharp
public AddAccidentSiteSystem();
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

- `Game.Events.AddAccidentSiteSystem+AddAccidentSiteJob`  
- `Game.Events.AddAccidentSiteSystem+TypeHandle`  

