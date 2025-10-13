# Colossal.Internal.Gizmos.GizmoFrustum

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoFrustum : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float4x4 trs;
    public System.Single fov;
    public System.Single minRange;
    public System.Single maxRange;
    public System.Single aspect;
    public UnityEngine.Color color;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate(System.Boolean ignoreMinRange);
    public static System.Int32 GetVertexCountEstimate(System.Boolean ignoreMinRange);
}
```


## Fields

- `public Unity.Mathematics.float4x4 trs`  

```csharp
public Unity.Mathematics.float4x4 trs;
```

- `public System.Single fov`  

```csharp
public System.Single fov;
```

- `public System.Single minRange`  

```csharp
public System.Single minRange;
```

- `public System.Single maxRange`  

```csharp
public System.Single maxRange;
```

- `public System.Single aspect`  

```csharp
public System.Single aspect;
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

- `public static GetIndexCountEstimate(System.Boolean ignoreMinRange) : System.Int32`  

```csharp
public static System.Int32 GetIndexCountEstimate(System.Boolean ignoreMinRange);
```

- `public static GetVertexCountEstimate(System.Boolean ignoreMinRange) : System.Int32`  

```csharp
public static System.Int32 GetVertexCountEstimate(System.Boolean ignoreMinRange);
```


