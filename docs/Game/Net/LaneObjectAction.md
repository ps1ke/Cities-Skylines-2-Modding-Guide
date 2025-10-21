# Game.Net.LaneObjectAction

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Net.LaneObjectAction>`  

## Code

```csharp
public sealed struct LaneObjectAction : System.IComparable<Game.Net.LaneObjectAction>
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Entities.Entity m_Remove;
    public Unity.Entities.Entity m_Add;
    public Unity.Mathematics.float2 m_CurvePosition;

    public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove);
    public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition);
    public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition);

    public System.Int32 CompareTo(Game.Net.LaneObjectAction other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Entities.Entity m_Remove`  

```csharp
public Unity.Entities.Entity m_Remove;
```

- `public Unity.Entities.Entity m_Add`  

```csharp
public Unity.Entities.Entity m_Add;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```


## Constructors

- `public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove)`  

```csharp
public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove);
```

- `public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition)`  

```csharp
public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition);
```

- `public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition)`  

```csharp
public LaneObjectAction(Unity.Entities.Entity lane, Unity.Entities.Entity remove, Unity.Entities.Entity add, Unity.Mathematics.float2 curvePosition);
```


## Methods

- `public CompareTo(Game.Net.LaneObjectAction other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Net.LaneObjectAction other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


