# Colossal.GizmoBatcher

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> m_CameraInfos`  
- `private Unity.Collections.NativeList<Unity.Mathematics.float4> m_CullingPlanes`  
- `private Colossal.Internal.Gizmos.GizmoObjects+Concurrent m_GizmoObjects`  
- `private Colossal.NativeCounter+Concurrent m_VertexCounter`  
- `private Colossal.NativeCounter+Concurrent m_IndexCounter`  

## Constructors

- `public GizmoBatcher(Colossal.Internal.Gizmos.GizmoObjects& gizmoObjects, Colossal.NativeCounter& vertexCounter, Colossal.NativeCounter& indexCounter, Unity.Collections.NativeList<Colossal.GizmoBatcher+CameraInfo> cameraInfos, Unity.Collections.NativeList<Unity.Mathematics.float4> cullingPlanes)`  

## Methods

- `private CheckCulling(Colossal.Mathematics.Bounds3 bounds, System.Single& pixelSize) : System.Boolean`  
- `public DrawArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  
- `public DrawArrowHead(Unity.Mathematics.float3 pos, Unity.Mathematics.float3 dir, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  
- `public DrawBezier(Colossal.Mathematics.Bezier4x3 bezier, UnityEngine.Color color, System.Single length = 1, System.Int32 segmentsCount = 16) : System.Void`  
- `public DrawCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Int32 segmentsCount = -1) : System.Void`  
- `public DrawDirectionalCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Boolean reverse = False, System.Int32 segmentsCount = 16, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  
- `public DrawFlowCurve(Colossal.Mathematics.Bezier4x3 bezier, System.Single length, UnityEngine.Color color, System.Single timeOffset = 0, System.Boolean reverse = False, System.Int32 arrowCount = 2, System.Int32 segmentsCount = 16, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  
- `public DrawLine(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color) : System.Void`  
- `public DrawMiddleArrow(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, UnityEngine.Color color, System.Single headLength = 0,4, System.Single headAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  
- `public DrawRay(Unity.Mathematics.float3 start, Unity.Mathematics.float3 direction, UnityEngine.Color color) : System.Void`  
- `public DrawWireArc(Unity.Mathematics.float3 center, Unity.Mathematics.float3 normal, Unity.Mathematics.float3 from, System.Single angle, System.Single radius, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  
- `public DrawWireBounds(UnityEngine.Bounds bounds, UnityEngine.Color color) : System.Void`  
- `public DrawWireBounds(Unity.Mathematics.float4x4 trs, UnityEngine.Bounds bounds, UnityEngine.Color color) : System.Void`  
- `public DrawWireCapsule(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCapsule(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCapsuleConic(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCapsuleConic(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCircleFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, UnityEngine.Color color, System.Int32 segmentsCount = 36) : System.Void`  
- `public DrawWireCone(Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCone(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 a, System.Single radiusA, Unity.Mathematics.float3 b, System.Single radiusB, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCube(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color) : System.Void`  
- `public DrawWireCube(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, UnityEngine.Color color) : System.Void`  
- `public DrawWireCylinder(Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireCylinder(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, System.Single radius, System.Single height, UnityEngine.Color color, System.Int32 circleSegmentsCount = 36) : System.Void`  
- `public DrawWireFrustum(Unity.Mathematics.float4x4 trs, System.Single fov, System.Single minRange, System.Single maxRange, System.Single aspect, UnityEngine.Color color) : System.Void`  
- `public DrawWireNode(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color) : System.Void`  
- `public DrawWireRect(Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color) : System.Void`  
- `public DrawWireRect(Unity.Mathematics.float4x4 trs, Unity.Mathematics.float3 center, Unity.Mathematics.float2 size, UnityEngine.Color color) : System.Void`  
- `public DrawWireSphere(Unity.Mathematics.float3 center, System.Single radius, UnityEngine.Color color, System.Int32 slicesX = 1, System.Int32 slicesY = 2, System.Int32 slicesZ = 0, System.Int32 segmentsCount = 36) : System.Void`  

## Nested types

- `Colossal.GizmoBatcher+CameraInfo`  

