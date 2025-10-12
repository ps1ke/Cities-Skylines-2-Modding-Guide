# Game.Rendering.OverlayRenderSystem+Buffer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedCurves`  
- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteCurves`  
- `private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_Bounds`  
- `private System.Single m_PositionY`  
- `private System.Single m_ScaleY`  

## Constructors

- `public Buffer(Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> projectedCurves, Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> absoluteCurves, Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> bounds, System.Single positionY, System.Single scaleY)`  

## Methods

- `private static BuildCurveMatrix(Colossal.Mathematics.Bezier4x3 curve, System.Single length) : Unity.Mathematics.float4x4`  
- `public DrawCircle(UnityEngine.Color color, Unity.Mathematics.float3 position, System.Single diameter) : System.Void`  
- `public DrawCircle(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter) : System.Void`  
- `private DrawCircleImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter) : System.Void`  
- `public DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width) : System.Void`  
- `public DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width) : System.Void`  
- `public DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  
- `public DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  
- `private DrawCurveImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness, System.Single length) : System.Void`  
- `public DrawDashedCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  
- `public DrawDashedCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  
- `public DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  
- `public DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  
- `public DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness) : System.Void`  
- `public DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness) : System.Void`  
- `public DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width) : System.Void`  
- `public DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width) : System.Void`  
- `public DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  
- `public DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  
- `private FitBox(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  
- `private FitBox(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  
- `private FitQuad(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  
- `private FitQuad(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  

