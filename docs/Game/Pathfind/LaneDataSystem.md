# Game.Pathfind.LaneDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneDataSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_LaneQuery2;
    private Game.Pathfind.LaneDataSystem+TypeHandle __TypeHandle;

    public LaneDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery2`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery2;
```

- `private Game.Pathfind.LaneDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LaneDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneDataSystem()`  

```csharp
public LaneDataSystem();
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

- `Game.Pathfind.LaneDataSystem+UpdateLaneDataJob`  
- `Game.Pathfind.LaneDataSystem+UpdateLaneData2Job`  
- `Game.Pathfind.LaneDataSystem+TypeHandle`  

