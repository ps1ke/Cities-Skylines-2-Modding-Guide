# Colossal.Internal.Gizmos.GizmoLine

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Internal.Gizmos.IGizmoObject`  

## Code

```csharp
public sealed struct GizmoLine : Colossal.Internal.Gizmos.IGizmoObject
{
    public Unity.Mathematics.float3 a;
    public Unity.Mathematics.float3 b;
    public UnityEngine.Color color;

    public System.Void BuildRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
    public static System.Int32 GetIndexCountEstimate();
    public static System.Int32 GetVertexCountEstimate();
}
```


## Fields

- `public Unity.Mathematics.float3 a`  

```csharp
public Unity.Mathematics.float3 a;
```

- `public Unity.Mathematics.float3 b`  

```csharp
public Unity.Mathematics.float3 b;
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


