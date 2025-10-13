# Colossal.Internal.Gizmos.GizmoArrowHead

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoArrowHead : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float3 startpos;
    public Unity.Mathematics.float3 dir;
    public UnityEngine.Color color;
    public System.Single headLength;
    public System.Single headAngle;
    public System.Int32 circleSegmentsCount;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate(System.Int32 segments);
    public static System.Int32 GetVertexCountEstimate(System.Int32 segments);
}
```


## Fields

- `public Unity.Mathematics.float3 startpos`  

```csharp
public Unity.Mathematics.float3 startpos;
```

- `public Unity.Mathematics.float3 dir`  

```csharp
public Unity.Mathematics.float3 dir;
```

- `public UnityEngine.Color color`  

```csharp
public UnityEngine.Color color;
```

- `public System.Single headLength`  

```csharp
public System.Single headLength;
```

- `public System.Single headAngle`  

```csharp
public System.Single headAngle;
```

- `public System.Int32 circleSegmentsCount`  

```csharp
public System.Int32 circleSegmentsCount;
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


