# Game.Tools.SnapLine

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SnapLine
{
    public Game.Tools.ControlPoint m_ControlPoint;
    public Colossal.Mathematics.Bezier4x3 m_Curve;
    public Game.Tools.SnapLineFlags m_Flags;
    public System.Single m_HeightWeight;

    public SnapLine(Game.Tools.ControlPoint position, Colossal.Mathematics.Bezier4x3 curve, Game.Tools.SnapLineFlags flags, System.Single heightWeight);

}
```


## Fields

- `public Game.Tools.ControlPoint m_ControlPoint`  

```csharp
public Game.Tools.ControlPoint m_ControlPoint;
```

- `public Colossal.Mathematics.Bezier4x3 m_Curve`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Curve;
```

- `public Game.Tools.SnapLineFlags m_Flags`  

```csharp
public Game.Tools.SnapLineFlags m_Flags;
```

- `public System.Single m_HeightWeight`  

```csharp
public System.Single m_HeightWeight;
```


## Constructors

- `public SnapLine(Game.Tools.ControlPoint position, Colossal.Mathematics.Bezier4x3 curve, Game.Tools.SnapLineFlags flags, System.Single heightWeight)`  

```csharp
public SnapLine(Game.Tools.ControlPoint position, Colossal.Mathematics.Bezier4x3 curve, Game.Tools.SnapLineFlags flags, System.Single heightWeight);
```


