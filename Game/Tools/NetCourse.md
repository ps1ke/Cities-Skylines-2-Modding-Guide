# Game.Tools.NetCourse

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct NetCourse : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Tools.CoursePos m_StartPosition;
    public Game.Tools.CoursePos m_EndPosition;
    public Colossal.Mathematics.Bezier4x3 m_Curve;
    public Unity.Mathematics.float2 m_Elevation;
    public System.Single m_Length;
    public System.Int32 m_FixedIndex;

}
```


## Fields

- `public Game.Tools.CoursePos m_StartPosition`  

```csharp
public Game.Tools.CoursePos m_StartPosition;
```

- `public Game.Tools.CoursePos m_EndPosition`  

```csharp
public Game.Tools.CoursePos m_EndPosition;
```

- `public Colossal.Mathematics.Bezier4x3 m_Curve`  

```csharp
public Colossal.Mathematics.Bezier4x3 m_Curve;
```

- `public Unity.Mathematics.float2 m_Elevation`  

```csharp
public Unity.Mathematics.float2 m_Elevation;
```

- `public System.Single m_Length`  

```csharp
public System.Single m_Length;
```

- `public System.Int32 m_FixedIndex`  

```csharp
public System.Int32 m_FixedIndex;
```


