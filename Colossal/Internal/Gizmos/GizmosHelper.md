# Colossal.Internal.Gizmos.GizmosHelper

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class GizmosHelper
{
    public static System.Void DrawBezier(Colossal.Internal.Gizmos.RenderData& renderData, Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length, System.Int32 segmentCount);
    public static System.Void DrawLine(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color);
    public static System.Void DrawWireArc(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount);
    public static System.Void DrawWireArrowHead(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 startpos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
    public static System.Void DrawWireCapsule(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 segmentsCount);
    public static System.Void DrawWireCapsuleConic(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 segmentsCount);
    public static System.Void DrawWireCone(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 segmentsCount);
    public static System.Void DrawWireCube(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color);
    public static System.Void DrawWireCylinder(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 segmentsCount);
    public static System.Void DrawWireFrustum(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color);
    public static System.Void DrawWireSphere(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ, System.Int32 segmentsCount);
    public static System.Int32 EstimatePointsVsLength(System.Single length);
}
```


## Methods

- `public static DrawBezier(Colossal.Internal.Gizmos.RenderData& renderData, Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length = 1, System.Int32 segmentCount = -1) : System.Void`  

```csharp
public static System.Void DrawBezier(Colossal.Internal.Gizmos.RenderData& renderData, Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length, System.Int32 segmentCount);
```

- `public static DrawLine(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color) : System.Void`  

```csharp
public static System.Void DrawLine(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color);
```

- `public static DrawWireArc(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount = 40) : System.Void`  

```csharp
public static System.Void DrawWireArc(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public static DrawWireArrowHead(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 startpos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public static System.Void DrawWireArrowHead(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 startpos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
```

- `public static DrawWireCapsule(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public static System.Void DrawWireCapsule(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public static DrawWireCapsuleConic(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public static System.Void DrawWireCapsuleConic(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public static DrawWireCone(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public static System.Void DrawWireCone(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public static DrawWireCube(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color) : System.Void`  

```csharp
public static System.Void DrawWireCube(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color);
```

- `public static DrawWireCylinder(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public static System.Void DrawWireCylinder(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public static DrawWireFrustum(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color) : System.Void`  

```csharp
public static System.Void DrawWireFrustum(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color);
```

- `public static DrawWireSphere(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX = 1, System.Int32 slicesY = 2, System.Int32 slicesZ = 0, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public static System.Void DrawWireSphere(Colossal.Internal.Gizmos.RenderData& renderData, Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ, System.Int32 segmentsCount);
```

- `public static EstimatePointsVsLength(System.Single length) : System.Int32`  

```csharp
public static System.Int32 EstimatePointsVsLength(System.Single length);
```


