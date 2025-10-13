# Colossal.Internal.Gizmos.GizmoSphere

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoSphere : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float3 center;
    public System.Single radius;
    public UnityEngine.Color color;
    public System.Int32 segmentsCount;
    public System.Int32 slicesX;
    public System.Int32 slicesY;
    public System.Int32 slicesZ;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate(System.Int32 segments, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ);
    public static System.Int32 GetVertexCountEstimate(System.Int32 segments, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ);
}
```


## Fields

- `public Unity.Mathematics.float3 center`  

```csharp
public Unity.Mathematics.float3 center;
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

- `public System.Int32 slicesX`  

```csharp
public System.Int32 slicesX;
```

- `public System.Int32 slicesY`  

```csharp
public System.Int32 slicesY;
```

- `public System.Int32 slicesZ`  

```csharp
public System.Int32 slicesZ;
```


## Methods

- `public BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData) : System.Void`  

```csharp
public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
```

- `public static GetIndexCountEstimate(System.Int32 segments, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ) : System.Int32`  

```csharp
public static System.Int32 GetIndexCountEstimate(System.Int32 segments, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ);
```

- `public static GetVertexCountEstimate(System.Int32 segments, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ) : System.Int32`  

```csharp
public static System.Int32 GetVertexCountEstimate(System.Int32 segments, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ);
```


