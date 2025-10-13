# Game.Tools.BrushDefinition

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct BrushDefinition : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Tool;
    public Colossal.Mathematics.Line3+Segment m_Line;
    public System.Single m_Angle;
    public System.Single m_Size;
    public System.Single m_Strength;
    public System.Single m_Time;
    public Unity.Mathematics.float3 m_Target;
    public Unity.Mathematics.float3 m_Start;

}
```


## Fields

- `public Unity.Entities.Entity m_Tool`  

```csharp
public Unity.Entities.Entity m_Tool;
```

- `public Colossal.Mathematics.Line3+Segment m_Line`  

```csharp
public Colossal.Mathematics.Line3+Segment m_Line;
```

- `public System.Single m_Angle`  

```csharp
public System.Single m_Angle;
```

- `public System.Single m_Size`  

```csharp
public System.Single m_Size;
```

- `public System.Single m_Strength`  

```csharp
public System.Single m_Strength;
```

- `public System.Single m_Time`  

```csharp
public System.Single m_Time;
```

- `public Unity.Mathematics.float3 m_Target`  

```csharp
public Unity.Mathematics.float3 m_Target;
```

- `public Unity.Mathematics.float3 m_Start`  

```csharp
public Unity.Mathematics.float3 m_Start;
```


