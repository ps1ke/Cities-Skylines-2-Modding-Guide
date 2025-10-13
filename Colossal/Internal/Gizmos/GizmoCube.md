# Colossal.Internal.Gizmos.GizmoCube

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoCube : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float4x4 trs;
    public Unity.Mathematics.float3 center;
    public Unity.Mathematics.float3 size;
    public UnityEngine.Color color;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate();
    public static System.Int32 GetVertexCountEstimate();
}
```


## Fields

- `public Unity.Mathematics.float4x4 trs`  

```csharp
public Unity.Mathematics.float4x4 trs;
```

- `public Unity.Mathematics.float3 center`  

```csharp
public Unity.Mathematics.float3 center;
```

- `public Unity.Mathematics.float3 size`  

```csharp
public Unity.Mathematics.float3 size;
```

- `public UnityEngine.Color color`  

```csharp
public UnityEngine.Color color;
```


## Methods

- `public BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData) : System.Void`  

```csharp
public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
```

- `public static GetIndexCountEstimate() : System.Int32`  

```csharp
public static System.Int32 GetIndexCountEstimate();
```

- `public static GetVertexCountEstimate() : System.Int32`  

```csharp
public static System.Int32 GetVertexCountEstimate();
```


