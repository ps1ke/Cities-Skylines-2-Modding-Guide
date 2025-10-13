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
public static void DrawCurve(this GizmoBatcher batcher, Curve curve, Color color, int segmentsCount = -1)
	{
		batcher.DrawCurve(curve.m_Bezier, curve.m_Length, color, segmentsCount);
	}
```

- `public static DrawDirectionalCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Boolean reverse = False, System.Int32 segmentsCount = -1, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public static void DrawDirectionalCurve(this GizmoBatcher batcher, Curve curve, Color color, bool reverse = false, int segmentsCount = -1, float arrowHeadLength = 0.4f, float arrowHeadAngle = 25f, int circleSegmentsCount = 16)
	{
		batcher.DrawDirectionalCurve(curve.m_Bezier, curve.m_Length, color, reverse, segmentsCount, arrowHeadLength, arrowHeadAngle, circleSegmentsCount);
	}
```

- `public static DrawFlowCurve(Colossal.GizmoBatcher batcher, Game.Net.Curve curve, UnityEngine.Color color, System.Single timeOffset = 0, System.Boolean reverse = False, System.Int32 arrowCount = 2, System.Int32 segmentsCount = 16, System.Single arrowHeadLength = 0,4, System.Single arrowHeadAngle = 25, System.Int32 circleSegmentsCount = 16) : System.Void`  

```csharp
public static void DrawFlowCurve(this GizmoBatcher batcher, Curve curve, Color color, float timeOffset = 0f, bool reverse = false, int arrowCount = 2, int segmentsCount = 16, float arrowHeadLength = 0.4f, float arrowHeadAngle = 25f, int circleSegmentsCount = 16)
	{
		batcher.DrawFlowCurve(curve.m_Bezier, curve.m_Length, color, timeOffset, reverse, arrowCount, segmentsCount, arrowHeadLength, arrowHeadAngle, circleSegmentsCount);
	}
```


