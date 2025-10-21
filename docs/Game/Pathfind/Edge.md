# Game.Pathfind.Edge

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Edge
{
    public Unity.Entities.Entity m_Owner;
    public Game.Pathfind.NodeID m_StartID;
    public Game.Pathfind.NodeID m_MiddleID;
    public Game.Pathfind.NodeID m_EndID;
    public System.Single m_StartCurvePos;
    public System.Single m_EndCurvePos;
    public Game.Pathfind.PathSpecification m_Specification;
    public Game.Pathfind.LocationSpecification m_Location;

}
```


## Fields

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```

- `public Game.Pathfind.NodeID m_StartID`  

```csharp
public Game.Pathfind.NodeID m_StartID;
```

- `public Game.Pathfind.NodeID m_MiddleID`  

```csharp
public Game.Pathfind.NodeID m_MiddleID;
```

- `public Game.Pathfind.NodeID m_EndID`  

```csharp
public Game.Pathfind.NodeID m_EndID;
```

- `public System.Single m_StartCurvePos`  

```csharp
public System.Single m_StartCurvePos;
```

- `public System.Single m_EndCurvePos`  

```csharp
public System.Single m_EndCurvePos;
```

- `public Game.Pathfind.PathSpecification m_Specification`  

```csharp
public Game.Pathfind.PathSpecification m_Specification;
```

- `public Game.Pathfind.LocationSpecification m_Location`  

```csharp
public Game.Pathfind.LocationSpecification m_Location;
```


