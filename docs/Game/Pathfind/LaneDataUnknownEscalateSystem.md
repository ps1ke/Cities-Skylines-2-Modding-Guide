# Game.Pathfind.LaneDataUnknownEscalateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneDataUnknownEscalateSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Pathfind.LaneDataUnknownEscalateSystem+TypeHandle __TypeHandle;

    public LaneDataUnknownEscalateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Pathfind.LaneDataUnknownEscalateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LaneDataUnknownEscalateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneDataUnknownEscalateSystem()`  

```csharp
public LaneDataUnknownEscalateSystem();
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

- `Game.Pathfind.LaneDataUnknownEscalateSystem+LaneDataUnknownEscalateJob`  
- `Game.Pathfind.LaneDataUnknownEscalateSystem+TypeHandle`  

