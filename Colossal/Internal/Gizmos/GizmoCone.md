# Colossal.Internal.Gizmos.GizmoCone

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoCone : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float4x4 trs;
    public Unity.Mathematics.float3 a;
    public System.Single radiusA;
    public Unity.Mathematics.float3 b;
    public System.Single radiusB;
    public UnityEngine.Color color;
    public System.Int32 circleSegmentsCount;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate(System.Int32 segments);
    public static System.Int32 GetVertexCountEstimate(System.Int32 segments);
}
```


## Fields

- `public Unity.Mathematics.float4x4 trs`  

```csharp
public Unity.Mathematics.float4x4 trs;
```

- `public Unity.Mathematics.float3 a`  

```csharp
public Unity.Mathematics.float3 a;
```

- `public System.Single radiusA`  

```csharp
public System.Single radiusA;
```

- `public Unity.Mathematics.float3 b`  

```csharp
public Unity.Mathematics.float3 b;
```

- `public System.Single radiusB`  

```csharp
public System.Single radiusB;
```

- `public UnityEngine.Color color`  

```csharp
public UnityEngine.Color color;
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


