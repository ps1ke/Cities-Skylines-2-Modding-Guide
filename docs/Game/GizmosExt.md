# Game.GizmosExt

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class GizmosExt
{
    public static System.Void DrawCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Int32 segmentsCount);
    public static System.Void DrawDirectionalCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Boolean reverse, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
    public static System.Void DrawFlowCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Single timeOffset, System.Boolean reverse, System.Int32 arrowCount, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
}
```


## Methods

- `public static DrawCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Int32 segmentsCount = -1) : System.Void`  

```csharp
public static System.Void DrawCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Int32 segmentsCount);
```

- `public static DrawDirectionalCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Boolean reverse = False, System.Int32 segmentsCount = -1, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public static System.Void DrawDirectionalCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Boolean reverse, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
```

- `public static DrawFlowCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Single timeOffset = 0, System.Boolean reverse = False, System.Int32 arrowCount = 2, System.Int32 segmentsCount = 16, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public static System.Void DrawFlowCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Single timeOffset, System.Boolean reverse, System.Int32 arrowCount, System.Int32 segmentsCount, System.Single arrowHeadLength, System.Single arrowHeadAngle, System.Int32 circleSegmentsCount);
```


