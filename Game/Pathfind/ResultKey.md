# Game.Pathfind.PathfindResultSystem+ResultKey

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Pathfind.PathfindResultSystem+ResultKey>`  

## Code

```csharp
public sealed struct ResultKey : System.IEquatable<Game.Pathfind.PathfindResultSystem+ResultKey>
{
    public System.Object m_System;
    public Game.Pathfind.PathfindResultSystem+QueryType m_QueryType;
    public Game.Pathfind.SetupTargetType m_OriginType;
    public Game.Pathfind.SetupTargetType m_DestinationType;

    public System.Boolean Equals(Game.Pathfind.PathfindResultSystem+ResultKey other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public System.Object m_System`  

```csharp
public System.Object m_System;
```

- `public Game.Pathfind.PathfindResultSystem+QueryType m_QueryType`  

```csharp
public Game.Pathfind.PathfindResultSystem+QueryType m_QueryType;
```

- `public Game.Pathfind.SetupTargetType m_OriginType`  

```csharp
public Game.Pathfind.SetupTargetType m_OriginType;
```

- `public Game.Pathfind.SetupTargetType m_DestinationType`  

```csharp
public Game.Pathfind.SetupTargetType m_DestinationType;
```


## Methods

- `public Equals(Game.Pathfind.PathfindResultSystem+ResultKey other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Pathfind.PathfindResultSystem+ResultKey other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


