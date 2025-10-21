# Game.Simulation.TrainNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrainNavigationSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle;

    public TrainNavigationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrainNavigationSystem()`  

```csharp
public TrainNavigationSystem();
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

- `Game.Simulation.TrainNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.TrainNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.TrainNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.TrainNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.TrainNavigationSystem+TypeHandle`  

