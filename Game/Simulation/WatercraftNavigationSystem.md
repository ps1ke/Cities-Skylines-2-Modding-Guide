# Game.Simulation.WatercraftNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WatercraftNavigationSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
    private Game.Simulation.WatercraftNavigationSystem+TypeHandle __TypeHandle;

    public WatercraftNavigationSystem();

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

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  

```csharp
private Game.Net.LaneObjectUpdater m_LaneObjectUpdater;
```

- `private Game.Simulation.WatercraftNavigationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WatercraftNavigationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WatercraftNavigationSystem()`  

```csharp
public WatercraftNavigationSystem();
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

- `Game.Simulation.WatercraftNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.WatercraftNavigationSystem+GroupLaneReservationsJob`  
- `Game.Simulation.WatercraftNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.WatercraftNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.WatercraftNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.WatercraftNavigationSystem+TypeHandle`  

