# Game.GizmosExt

**Assembly:** Assembly-CSharp (typical game assembly; may vary in modding context)  
**Namespace:** Game

**Type:** public static class

**Base:** System.Object

**Summary:** Extension methods for GizmoBatcher that make it convenient to draw Curve objects (game-specific Curve type) using existing GizmoBatcher APIs. Each method forwards the call to corresponding GizmoBatcher overloads that accept a curve's internal Bezier and length values. These helpers simplify rendering of plain, directional, and flowing curves with optional arrowheads and circle markers.

---

## Fields

- None.  
This static class contains no instance or static fields; it only provides extension methods.

## Properties

- None.  
There are no properties on this static helper class.

## Constructors

- None.  
As a static class, GizmosExt has no public constructors. Its methods are static extension methods and are used without instantiating the class.

## Methods

- public static void DrawCurve(this GizmoBatcher batcher, Curve curve, Color color, int segmentsCount = -1)  
Draws a Curve using the provided GizmoBatcher. This is a convenience wrapper that extracts the curve's internal Bezier representation and length and forwards them to the underlying GizmoBatcher drawing implementation.

  Parameters:
  - batcher: The GizmoBatcher instance to extend (use via extension method syntax).
  - curve: The Curve instance to draw (uses curve.m_Bezier and curve.m_Length).
  - color: Color to draw the curve with.
  - segmentsCount: Optional number of segments to subdivide the curve into. Default -1 lets the underlying implementation choose an appropriate segment count.

  Remarks:
  - This method simply calls batcher.DrawCurve(curve.m_Bezier, curve.m_Length, color, segmentsCount).

- public static void DrawDirectionalCurve(this GizmoBatcher batcher, Curve curve, Color color, bool reverse = false, int segmentsCount = -1, float arrowHeadLength = 0.4f, float arrowHeadAngle = 25f, int circleSegmentsCount = 16)  
Draws a Curve with directional markers (arrowheads and optional circle markers) using the GizmoBatcher. Forwarding wrapper that passes the curve's Bezier and length to the underlying GizmoBatcher.

  Parameters:
  - batcher: The GizmoBatcher instance to extend.
  - curve: The Curve to draw.
  - color: Color to use for the curve and markers.
  - reverse: If true, arrows/markers will point in the reverse direction along the curve.
  - segmentsCount: Optional subdivision count for the curve; default -1 defers to the underlying implementation.
  - arrowHeadLength: Length of the arrow head in world units (default 0.4f).
  - arrowHeadAngle: Angle of the arrow head in degrees (default 25f).
  - circleSegmentsCount: Number of segments to use when drawing circle markers (default 16).

  Remarks:
  - This helper calls batcher.DrawDirectionalCurve(curve.m_Bezier, curve.m_Length, ...).

- public static void DrawFlowCurve(this GizmoBatcher batcher, Curve curve, Color color, float timeOffset = 0f, bool reverse = false, int arrowCount = 2, int segmentsCount = 16, float arrowHeadLength = 0.4f, float arrowHeadAngle = 25f, int circleSegmentsCount = 16)  
Draws a flowing/directional curve visualization, where arrows (or other flow indicators) are placed along the curve and may be offset in time to create a motion effect. This is a wrapper that feeds the curve's Bezier and length into the corresponding GizmoBatcher flow-drawing method.

  Parameters:
  - batcher: The GizmoBatcher instance to extend.
  - curve: The Curve instance to draw.
  - color: Color for the curve and flow markers.
  - timeOffset: Time offset used to vary arrow positions over time (default 0f).
  - reverse: If true, arrows flow in the reverse direction.
  - arrowCount: How many arrows (flow indicators) to draw along the curve (default 2).
  - segmentsCount: Number of segments to approximate the curve (default 16).
  - arrowHeadLength: World length of arrow heads (default 0.4f).
  - arrowHeadAngle: Arrow head angle in degrees (default 25f).
  - circleSegmentsCount: Segments used for circle markers (default 16).

  Remarks:
  - This calls batcher.DrawFlowCurve(curve.m_Bezier, curve.m_Length, ...).

Usage notes:
- These are extension methods; ensure you have `using Game;` (or the appropriate namespace) in scope to call them as instance-style methods on a GizmoBatcher: e.g. `batcher.DrawCurve(curve, Color.white);`
- The methods reference curve.m_Bezier and curve.m_Length, so they rely on the internal layout of the Curve type. Changes to that type in future game updates may require updating this wrapper.
- Dependencies/imports in the source: Colossal, Game.Net, UnityEngine — the extension methods rely on Unity's Color and the game's types (GizmoBatcher, Curve).

```csharp
using Colossal;
using Game.Net;
using UnityEngine;

namespace Game
{
	public static class GizmosExt
	{
		public static void DrawCurve(this GizmoBatcher batcher, Curve curve, Color color, int segmentsCount = -1)
		{
			batcher.DrawCurve(curve.m_Bezier, curve.m_Length, color, segmentsCount);
		}

		public static void DrawDirectionalCurve(this GizmoBatcher batcher, Curve curve, Color color, bool reverse = false, int segmentsCount = -1, float arrowHeadLength = 0.4f, float arrowHeadAngle = 25f, int circleSegmentsCount = 16)
		{
			batcher.DrawDirectionalCurve(curve.m_Bezier, curve.m_Length, color, reverse, segmentsCount, arrowHeadLength, arrowHeadAngle, circleSegmentsCount);
		}

		public static void DrawFlowCurve(this GizmoBatcher batcher, Curve curve, Color color, float timeOffset = 0f, bool reverse = false, int arrowCount = 2, int segmentsCount = 16, float arrowHeadLength = 0.4f, float arrowHeadAngle = 25f, int circleSegmentsCount = 16)
		{
			batcher.DrawFlowCurve(curve.m_Bezier, curve.m_Length, color, timeOffset, reverse, arrowCount, segmentsCount, arrowHeadLength, arrowHeadAngle, circleSegmentsCount);
		}
	}
}
```