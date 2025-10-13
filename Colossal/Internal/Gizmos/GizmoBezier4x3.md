# Colossal.Internal.Gizmos.GizmoBezier4x3

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoBezier4x3 : Colossal.Internal.Gizmos.IGizmoObject
{
    public Colossal.Mathematics.Bezier4x3 bezier;
    public System.Single length;
    public UnityEngine.Color color;
    public System.Int32 segmentsCount;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate(System.Int32 segments);
    public static System.Int32 GetVertexCountEstimate(System.Int32 segments);
}
```


## Fields

- `public Colossal.Mathematics.Bezier4x3 bezier`  

```csharp
public Colossal.Mathematics.Bezier4x3 bezier;
```

- `public System.Single length`  

```csharp
public System.Single length;
```

- `public UnityEngine.Color color`  

```csharp
public UnityEngine.Color color;
```

- `public System.Int32 segmentsCount`  

```csharp
public System.Int32 segmentsCount;
```


## Methods

- `public BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData) : System.Void`  

```csharp
public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
```

- `public static GetIndexCountEstimate(System.Int32 segments) : System.Int32`  

```csharp
public static System.Int32 GetIndexCountEstimate(System.Int32 segments);
```

- `public static GetVertexCountEstimate(System.Int32 segments) : System.Int32`  

```csharp
public static System.Int32 GetVertexCountEstimate(System.Int32 segments);
```


