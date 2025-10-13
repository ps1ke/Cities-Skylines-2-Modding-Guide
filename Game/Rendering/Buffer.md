# Game.Rendering.OverlayRenderSystem+Buffer

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Buffer
{
    private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedCurves;
    private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteCurves;
    private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_Bounds;
    private System.Single m_PositionY;
    private System.Single m_ScaleY;

    public Buffer(Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> projectedCurves, Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> absoluteCurves, Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> bounds, System.Single positionY, System.Single scaleY);

    private static Unity.Mathematics.float4x4 BuildCurveMatrix(Colossal.Mathematics.Bezier4x3 curve, System.Single length);
    public System.Void DrawCircle(UnityEngine.Color color, Unity.Mathematics.float3 position, System.Single diameter);
    public System.Void DrawCircle(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter);
    private System.Void DrawCircleImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter);
    public System.Void DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width);
    public System.Void DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width);
    public System.Void DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness);
    public System.Void DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness);
    private System.Void DrawCurveImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness, System.Single length);
    public System.Void DrawDashedCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength);
    public System.Void DrawDashedCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength);
    public System.Void DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength);
    public System.Void DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength);
    public System.Void DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness);
    public System.Void DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness);
    public System.Void DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width);
    public System.Void DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width);
    public System.Void DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness);
    public System.Void DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness);
    private UnityEngine.Matrix4x4 FitBox(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
    private UnityEngine.Matrix4x4 FitBox(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
    private UnityEngine.Matrix4x4 FitQuad(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
    private UnityEngine.Matrix4x4 FitQuad(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
}
```


## Fields

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedCurves`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_ProjectedCurves;
```

- `private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteCurves`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> m_AbsoluteCurves;
```

- `private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_Bounds`  

```csharp
private Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> m_Bounds;
```

- `private System.Single m_PositionY`  

```csharp
private System.Single m_PositionY;
```

- `private System.Single m_ScaleY`  

```csharp
private System.Single m_ScaleY;
```


## Constructors

- `public Buffer(Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> projectedCurves, Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> absoluteCurves, Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> bounds, System.Single positionY, System.Single scaleY)`  

```csharp
public Buffer(Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> projectedCurves, Unity.Collections.NativeList<Game.Rendering.OverlayRenderSystem+CurveData> absoluteCurves, Colossal.Collections.NativeValue<Game.Rendering.OverlayRenderSystem+BoundsData> bounds, System.Single positionY, System.Single scaleY);
```


## Methods

- `private static BuildCurveMatrix(Colossal.Mathematics.Bezier4x3 curve, System.Single length) : Unity.Mathematics.float4x4`  

```csharp
private static Unity.Mathematics.float4x4 BuildCurveMatrix(Colossal.Mathematics.Bezier4x3 curve, System.Single length);
```

- `public DrawCircle(UnityEngine.Color color, Unity.Mathematics.float3 position, System.Single diameter) : System.Void`  

```csharp
public System.Void DrawCircle(UnityEngine.Color color, Unity.Mathematics.float3 position, System.Single diameter);
```

- `public DrawCircle(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter) : System.Void`  

```csharp
public System.Void DrawCircle(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter);
```

- `private DrawCircleImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter) : System.Void`  

```csharp
private System.Void DrawCircleImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single diameter);
```

- `public DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width) : System.Void`  

```csharp
public System.Void DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width);
```

- `public DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width) : System.Void`  

```csharp
public System.Void DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width);
```

- `public DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  

```csharp
public System.Void DrawCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness);
```

- `public DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  

```csharp
public System.Void DrawCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, Unity.Mathematics.float2 roundness);
```

- `private DrawCurveImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness, System.Single length) : System.Void`  

```csharp
private System.Void DrawCurveImpl(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness, System.Single length);
```

- `public DrawDashedCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  

```csharp
public System.Void DrawDashedCurve(UnityEngine.Color color, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength);
```

- `public DrawDashedCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  

```csharp
public System.Void DrawDashedCurve(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Bezier4x3 curve, System.Single width, System.Single dashLength, System.Single gapLength);
```

- `public DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  

```csharp
public System.Void DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength);
```

- `public DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength) : System.Void`  

```csharp
public System.Void DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength);
```

- `public DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness) : System.Void`  

```csharp
public System.Void DrawDashedLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness);
```

- `public DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness) : System.Void`  

```csharp
public System.Void DrawDashedLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, System.Single dashLength, System.Single gapLength, Unity.Mathematics.float2 roundness);
```

- `public DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width) : System.Void`  

```csharp
public System.Void DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width);
```

- `public DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width) : System.Void`  

```csharp
public System.Void DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width);
```

- `public DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  

```csharp
public System.Void DrawLine(UnityEngine.Color color, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness);
```

- `public DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness) : System.Void`  

```csharp
public System.Void DrawLine(UnityEngine.Color outlineColor, UnityEngine.Color fillColor, System.Single outlineWidth, Game.Rendering.OverlayRenderSystem+StyleFlags styleFlags, Colossal.Mathematics.Line3+Segment line, System.Single width, Unity.Mathematics.float2 roundness);
```

- `private FitBox(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  

```csharp
private UnityEngine.Matrix4x4 FitBox(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
```

- `private FitBox(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  

```csharp
private UnityEngine.Matrix4x4 FitBox(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
```

- `private FitQuad(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  

```csharp
private UnityEngine.Matrix4x4 FitQuad(Unity.Mathematics.float2 direction, Unity.Mathematics.float3 position, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
```

- `private FitQuad(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds) : UnityEngine.Matrix4x4`  

```csharp
private UnityEngine.Matrix4x4 FitQuad(Colossal.Mathematics.Bezier4x3 curve, System.Single extend, Colossal.Mathematics.Bounds3& bounds);
```


