# Game.Pathfind.ParkingLaneDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkingLaneDataSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Pathfind.ParkingLaneDataSystem+TypeHandle __TypeHandle;

    public ParkingLaneDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Pathfind.ParkingLaneDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.ParkingLaneDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ParkingLaneDataSystem()`  

```csharp
public ParkingLaneDataSystem();
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

- `Game.Pathfind.ParkingLaneDataSystem+UpdateLaneDataJob`  
- `Game.Pathfind.ParkingLaneDataSystem+TypeHandle`  

