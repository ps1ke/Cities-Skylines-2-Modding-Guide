# Colossal.Internal.Gizmos.GizmoArc

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoArc : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float3 center;
    public Unity.Mathematics.float3 normal;
    public Unity.Mathematics.float3 from;
    public System.Single angle;
    public System.Single radius;
    public UnityEngine.Color color;
    public System.Int32 segmentsCount;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate(System.Int32 segments);
    public static System.Int32 GetVertexCountEstimate(System.Int32 segments);
}
```


## Fields

- `public Unity.Mathematics.float3 center`  

```csharp
public Unity.Mathematics.float3 center;
```

- `public Unity.Mathematics.float3 normal`  

```csharp
public Unity.Mathematics.float3 normal;
```

- `public Unity.Mathematics.float3 from`  

```csharp
public Unity.Mathematics.float3 from;
```

- `public System.Single angle`  

```csharp
public System.Single angle;
```

- `public System.Single radius`  

```csharp
public System.Single radius;
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


