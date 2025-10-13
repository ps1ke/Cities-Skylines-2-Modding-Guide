# Colossal.GizmoBatcher

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct GizmoBatcher
{
    private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos;
    private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes;
    private Colossal.Internal.Gizmos.GizmoObjects+Concurrent m_GizmoObjects;
    private Colossal.NativeCounter+Concurrent m_VertexCounter;
    private Colossal.NativeCounter+Concurrent m_IndexCounter;

    public GizmoBatcher(Colossal.Internal.Gizmos.GizmoObjects& gizmoObjects, Colossal.NativeCounter& vertexCounter, Colossal.NativeCounter& indexCounter, Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> cameraInfos, Unity.Collections.NativeList<Unity.Mathematics.float4> cullingPlanes);

    private System.Boolean CheckCulling(Colossal.Mathematics.Bounds3 bounds, System.Single& pixelSize);
    public System.Void DrawArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
    public System.Void DrawArrowHead(Unity.Mathematics.float3 pos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
    public System.Void DrawBezier(Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length, System.Int32 segmentsCount);
    public System.Void DrawCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Int32 segmentsCount);
    public System.Void DrawDirectionalCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Boolean reverse, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
    public System.Void DrawFlowCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Single timeOffset, System.Boolean reverse, System.Int32 arrowCount, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
    public System.Void DrawLine(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color);
    public System.Void DrawMiddleArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
    public System.Void DrawRay(Unity.Mathematics.float3 start, Unity.Mathematics.float3 direction, UnityEngine.Color color);
    public System.Void DrawWireArc(Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount);
    public System.Void DrawWireBounds(UnityEngine.Bounds bounds, UnityEngine.Color color);
    public System.Void DrawWireBounds(Unity.Mathematics.float4x4 trs, UnityEngine.Bounds bounds, UnityEngine.Color color);
    public System.Void DrawWireCapsule(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCapsule(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCapsuleConic(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCapsuleConic(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCircleFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, UnityEngine.Color color, System.Int32 segmentsCount);
    public System.Void DrawWireCone(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCone(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCube(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color);
    public System.Void DrawWireCube(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color);
    public System.Void DrawWireCylinder(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireCylinder(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
    public System.Void DrawWireFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color);
    public System.Void DrawWireNode(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color);
    public System.Void DrawWireRect(Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color);
    public System.Void DrawWireRect(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color);
    public System.Void DrawWireSphere(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ, System.Int32 segmentsCount);
}
```


## Fields

- `private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos`  

```csharp
private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos;
```

- `private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes`  

```csharp
private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes;
```

- `private Colossal.Internal.Gizmos.GizmoObjects+Concurrent m_GizmoObjects`  

```csharp
private Colossal.Internal.Gizmos.GizmoObjects+Concurrent m_GizmoObjects;
```

- `private Colossal.NativeCounter+Concurrent m_VertexCounter`  

```csharp
private Colossal.NativeCounter+Concurrent m_VertexCounter;
```

- `private Colossal.NativeCounter+Concurrent m_IndexCounter`  

```csharp
private Colossal.NativeCounter+Concurrent m_IndexCounter;
```


## Constructors

- `public GizmoBatcher(Colossal.Internal.Gizmos.GizmoObjects& gizmoObjects, Colossal.NativeCounter& vertexCounter, Colossal.NativeCounter& indexCounter, Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> cameraInfos, Unity.Collections.NativeList<Unity.Mathematics.float4> cullingPlanes)`  

```csharp
public GizmoBatcher(Colossal.Internal.Gizmos.GizmoObjects& gizmoObjects, Colossal.NativeCounter& vertexCounter, Colossal.NativeCounter& indexCounter, Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> cameraInfos, Unity.Collections.NativeList<Unity.Mathematics.float4> cullingPlanes);
```


## Methods

- `private CheckCulling(Colossal.Mathematics.Bounds3 bounds, System.Single& pixelSize) : System.Boolean`  

```csharp
private System.Boolean CheckCulling(Colossal.Mathematics.Bounds3 bounds, System.Single& pixelSize);
```

- `public DrawArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public System.Void DrawArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
```

- `public DrawArrowHead(Unity.Mathematics.float3 pos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public System.Void DrawArrowHead(Unity.Mathematics.float3 pos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
```

- `public DrawBezier(Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length = 1, System.Int32 segmentsCount = 16) : System.Void`  

```csharp
public System.Void DrawBezier(Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length, System.Int32 segmentsCount);
```

- `public DrawCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Int32 segmentsCount = -1) : System.Void`  

```csharp
public System.Void DrawCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public DrawDirectionalCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Boolean reverse = False, System.Int32 segmentsCount = 16, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public System.Void DrawDirectionalCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Boolean reverse, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
```

- `public DrawFlowCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Single timeOffset = 0, System.Boolean reverse = False, System.Int32 arrowCount = 2, System.Int32 segmentsCount = 16, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public System.Void DrawFlowCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Single timeOffset, System.Boolean reverse, System.Int32 arrowCount, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
```

- `public DrawLine(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawLine(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color);
```

- `public DrawMiddleArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public System.Void DrawMiddleArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength, System.Single headAngle, System.Int32 circleSegmentsCount);
```

- `public DrawRay(Unity.Mathematics.float3 start, Unity.Mathematics.float3 direction, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawRay(Unity.Mathematics.float3 start, Unity.Mathematics.float3 direction, UnityEngine.Color color);
```

- `public DrawWireArc(Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireArc(Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public DrawWireBounds(UnityEngine.Bounds bounds, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireBounds(UnityEngine.Bounds bounds, UnityEngine.Color color);
```

- `public DrawWireBounds(Unity.Mathematics.float4x4 trs, UnityEngine.Bounds bounds, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireBounds(Unity.Mathematics.float4x4 trs, UnityEngine.Bounds bounds, UnityEngine.Color color);
```

- `public DrawWireCapsule(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCapsule(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCapsule(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCapsule(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCapsuleConic(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCapsuleConic(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCapsuleConic(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCapsuleConic(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCircleFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCircleFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public DrawWireCone(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCone(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCone(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCone(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCube(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireCube(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color);
```

- `public DrawWireCube(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireCube(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color);
```

- `public DrawWireCylinder(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCylinder(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireCylinder(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireCylinder(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount);
```

- `public DrawWireFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color);
```

- `public DrawWireNode(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireNode(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color);
```

- `public DrawWireRect(Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireRect(Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color);
```

- `public DrawWireRect(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color) : System.Void`  

```csharp
public System.Void DrawWireRect(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color);
```

- `public DrawWireSphere(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX = 1, System.Int32 slicesY = 2, System.Int32 slicesZ = 0, System.Int32 segmentsCount = 36) : System.Void`  

```csharp
public System.Void DrawWireSphere(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX, System.Int32 slicesY, System.Int32 slicesZ, System.Int32 segmentsCount);
```


## Nested types

- `Colossal.GizmoBatcher+CameraInfo`  

