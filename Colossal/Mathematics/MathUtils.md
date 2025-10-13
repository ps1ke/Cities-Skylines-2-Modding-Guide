# Colossal.Mathematics.MathUtils

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class MathUtils
{
    public static System.Single Acceleration(Colossal.Mathematics.Bezier4x1 curve, System.Single t);
    public static Unity.Mathematics.float2 Acceleration(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
    public static Unity.Mathematics.float3 Acceleration(Colossal.Mathematics.Bezier4x3 curve, System.Single t);
    public static System.Single Area(Colossal.Mathematics.Bounds2 bounds);
    public static System.Single Area(Colossal.Mathematics.Bounds3 bounds);
    public static System.Single Area(Colossal.Mathematics.Triangle2 triangle);
    public static System.Single Area(Colossal.Mathematics.Triangle3 triangle);
    public static System.Void AxisAngle(Unity.Mathematics.quaternion q, Unity.Mathematics.float3& axis, System.Single& angle);
    public static Colossal.Mathematics.Bounds1 Bounds(Colossal.Mathematics.Bezier4x1 curve);
    public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Bezier4x2 curve);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Bezier4x3 curve);
    public static Colossal.Mathematics.Bounds1 Bounds(System.Single a, System.Single b);
    public static Colossal.Mathematics.Bounds1 Bounds(Unity.Mathematics.float2 positions);
    public static Colossal.Mathematics.Bounds1 Bounds(Colossal.Mathematics.Line1+Segment line);
    public static Colossal.Mathematics.Bounds2 Bounds(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
    public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Line2+Segment line);
    public static Colossal.Mathematics.Bounds3 Bounds(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Line3+Segment line);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Box3 box);
    public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Circle2 circle);
    public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Quad2 quad);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Quad3 quad);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Sphere3 sphere);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Tetrahedron3 tetrahedron);
    public static Colossal.Mathematics.Bounds1 Bounds(Colossal.Mathematics.Triangle1 triangle);
    public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Triangle2 triangle);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Triangle3 triangle);
    public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron);
    public static Colossal.Mathematics.Box3 Box(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position);
    private static System.Boolean BoxIntersectHelper(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, Unity.Mathematics.quaternion rotate2to1, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean BoxIntersectHelper(Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Single Center(Colossal.Mathematics.Bounds1 bounds);
    public static Unity.Mathematics.float2 Center(Colossal.Mathematics.Bounds2 bounds);
    public static Unity.Mathematics.float3 Center(Colossal.Mathematics.Bounds3 bounds);
    public static Unity.Mathematics.float2 Center(Colossal.Mathematics.Quad2 quad);
    public static System.Single Clamp(System.Single position, Colossal.Mathematics.Bounds1 bounds);
    public static Unity.Mathematics.float2 Clamp(Unity.Mathematics.float2 position, Colossal.Mathematics.Bounds2 bounds);
    public static Unity.Mathematics.float3 Clamp(Unity.Mathematics.float3 position, Colossal.Mathematics.Bounds3 bounds);
    public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
    public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
    public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
    public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
    public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
    public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
    public static Unity.Mathematics.float2 ClampLength(Unity.Mathematics.float2 value, System.Single maxLength);
    public static Unity.Mathematics.float3 ClampLength(Unity.Mathematics.float3 value, System.Single maxLength);
    public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
    public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
    public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
    public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
    public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
    public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
    public static Colossal.Mathematics.Triangle2 Clockwise(Colossal.Mathematics.Triangle2 triangle);
    public static System.Single Curvature(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
    public static Colossal.Mathematics.Bezier4x1 Cut(Colossal.Mathematics.Bezier4x1 curve, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Bezier4x2 Cut(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Bezier4x3 Cut(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Bezier4x3 Cut(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1 bounds);
    public static Colossal.Mathematics.Line1+Segment Cut(Colossal.Mathematics.Line1 line, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Line1+Segment Cut(Colossal.Mathematics.Line1+Segment line, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Line2+Segment Cut(Colossal.Mathematics.Line2 line, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Line2+Segment Cut(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Line3+Segment Cut(Colossal.Mathematics.Line3 line, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Line3+Segment Cut(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2 t);
    private static System.Boolean CylinderBoxIntersectHelper(Colossal.Mathematics.Bounds3 rectBounds, Colossal.Mathematics.Bounds1 cylinderHeight, Colossal.Mathematics.Circle2 cylinderCircle, Unity.Mathematics.quaternion rotateBtoC, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
    private static System.Boolean CylinderBoxIntersectHelper(Colossal.Mathematics.Bounds1 height, Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
    private static System.Boolean CylinderBoxIntersectHelper(System.Single height, Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 c1, Unity.Mathematics.float3 d1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Unity.Mathematics.float3 c2, Unity.Mathematics.float3 d2, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
    private static System.Boolean CylinderBoxIntersectHelper2(Colossal.Mathematics.Bounds3 boxBounds, Colossal.Mathematics.Bounds1 cylinderHeight, Colossal.Mathematics.Circle2 cylinderCircle, Unity.Mathematics.quaternion rotateCtoB, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
    public static System.Single Determinant(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
    public static System.Single Determinant(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c);
    private static System.Boolean DifferentSide(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Colossal.Mathematics.Line2 line);
    public static System.Single Distance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.float2 range, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t);
    public static System.Single Distance(Colossal.Mathematics.Bounds1 bounds, System.Single position);
    public static System.Single Distance(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position);
    public static System.Single Distance(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2);
    public static System.Single Distance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position);
    public static System.Single Distance(Colossal.Mathematics.Line2 line, Unity.Mathematics.float2 position, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 position, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, Unity.Mathematics.float2& t);
    public static System.Single Distance(Colossal.Mathematics.Line3 line, Unity.Mathematics.float3 position, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3 position, System.Single& t);
    public static System.Single Distance(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Mathematics.float2& t);
    public static System.Single Distance(Colossal.Mathematics.Line3 line1, Colossal.Mathematics.Line3 line2, Unity.Mathematics.float2& t);
    public static System.Single Distance(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Unity.Mathematics.float2& t);
    public static System.Single Distance(Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.float3 position, Unity.Mathematics.float2& t);
    public static System.Single DistanceSquared(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& t);
    public static System.Single DistanceSquared(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.float2 range, System.Single& t);
    public static System.Single DistanceSquared(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position);
    public static System.Single DistanceSquared(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2);
    public static System.Single DistanceSquared(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position);
    public static System.Single DistanceSquared(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 position, System.Single& t);
    public static System.Single DistanceSquared(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3 position, System.Single& t);
    public static System.Void Divide(Colossal.Mathematics.Bezier4x1 input, Colossal.Mathematics.Bezier4x1& output1, Colossal.Mathematics.Bezier4x1& output2, System.Single t);
    public static System.Void Divide(Colossal.Mathematics.Bezier4x2 input, Colossal.Mathematics.Bezier4x2& output1, Colossal.Mathematics.Bezier4x2& output2, System.Single t);
    public static System.Void Divide(Colossal.Mathematics.Bezier4x3 input, Colossal.Mathematics.Bezier4x3& output1, Colossal.Mathematics.Bezier4x3& output2, System.Single t);
    public static Unity.Mathematics.float2 EncodeOctahedral(Unity.Mathematics.float3 n);
    public static Colossal.Mathematics.Bezier4x3 EndReflect(Colossal.Mathematics.Bezier4x3 curve);
    public static System.Single EndTangent(Colossal.Mathematics.Bezier4x1 curve);
    public static Unity.Mathematics.float2 EndTangent(Colossal.Mathematics.Bezier4x2 curve);
    public static Unity.Mathematics.float3 EndTangent(Colossal.Mathematics.Bezier4x3 curve);
    public static Colossal.Mathematics.Bounds1 Expand(Colossal.Mathematics.Bounds1 bounds, System.Single range);
    public static Colossal.Mathematics.Bounds2 Expand(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 range);
    public static Colossal.Mathematics.Bounds3 Expand(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 range);
    public static Colossal.Mathematics.Quad2 Expand(Colossal.Mathematics.Quad2 quad, System.Single t);
    public static System.Single Extents(Colossal.Mathematics.Bounds1 bounds);
    public static Unity.Mathematics.float2 Extents(Colossal.Mathematics.Bounds2 bounds);
    public static Unity.Mathematics.float3 Extents(Colossal.Mathematics.Bounds3 bounds);
    public static System.Single Incenter(Colossal.Mathematics.Triangle1 triangle, System.Single& radius);
    public static Unity.Mathematics.float2 Incenter(Colossal.Mathematics.Triangle2 triangle, System.Single& radius);
    public static Unity.Mathematics.float3 Incenter(Colossal.Mathematics.Triangle3 triangle, System.Single& radius);
    public static System.Boolean Intersect(Colossal.Mathematics.Bezier4x1 curve, System.Single position, System.Single& t, System.Int32 iterations);
    public static System.Boolean Intersect(Colossal.Mathematics.Bezier4x2 curve1, Colossal.Mathematics.Bezier4x2 curve2, Unity.Mathematics.float2& t, System.Int32 iterations);
    public static System.Boolean Intersect(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t, System.Int32 iterations);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2, Colossal.Mathematics.Bounds1& intersection);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds, System.Single position);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Circle2 circle);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position);
    public static System.Boolean Intersect(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float2 position);
    public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle1, Colossal.Mathematics.Circle2 circle2);
    public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Cylinder3 cylinder, Colossal.Mathematics.Box3 box, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
    public static System.Boolean Intersect(Colossal.Mathematics.Line1 line, System.Single position, System.Single& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Line1+Segment line, System.Single position, System.Single& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds, Colossal.Mathematics.Line1+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Line2 line1, Colossal.Mathematics.Line2 line2, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2 line2, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Unity.Mathematics.float2 position);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Quad2 quad);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad1, Colossal.Mathematics.Quad2 quad2);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Triangle2 triangle);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Circle2 circle);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Quad2 quad, System.Single& area);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad3 quad, Colossal.Mathematics.Line3 line, System.Single& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Quad3 quad, Colossal.Mathematics.Line3+Segment line, System.Single& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere, Unity.Mathematics.float3 position);
    public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere1, Colossal.Mathematics.Sphere3 sphere2);
    public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere, Colossal.Mathematics.Line3 line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Tetrahedron3 tetrahedron, Unity.Mathematics.float3 position, Unity.Mathematics.float3& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Triangle2 triangle);
    public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Triangle2 triangle, System.Single& area);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle1, Colossal.Mathematics.Triangle2 triangle2);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Circle2 circle);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle3 triangle, Colossal.Mathematics.Line3 line, Unity.Mathematics.float3& t);
    public static System.Boolean Intersect(Colossal.Mathematics.Triangle3 triangle, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3& t);
    public static System.Boolean Intersect(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Int32 IntPow(System.Int32 b, System.Int32 exp);
    public static System.Single InverseSmoothStep(System.Single a, System.Single b, System.Single x);
    public static Unity.Mathematics.float2 InverseSmoothStep(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, Unity.Mathematics.float2 x);
    public static Unity.Mathematics.float3 InverseSmoothStep(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 x);
    public static Unity.Mathematics.float4 InverseSmoothStep(Unity.Mathematics.float4 a, Unity.Mathematics.float4 b, Unity.Mathematics.float4 x);
    public static Colossal.Mathematics.Bezier4x1 Invert(Colossal.Mathematics.Bezier4x1 curve);
    public static Colossal.Mathematics.Bezier4x2 Invert(Colossal.Mathematics.Bezier4x2 curve);
    public static Colossal.Mathematics.Bezier4x3 Invert(Colossal.Mathematics.Bezier4x3 curve);
    public static Colossal.Mathematics.Bounds1 Invert(Colossal.Mathematics.Bounds1 bounds);
    public static Colossal.Mathematics.Line1 Invert(Colossal.Mathematics.Line1 line);
    public static Colossal.Mathematics.Line1+Segment Invert(Colossal.Mathematics.Line1+Segment line);
    public static Colossal.Mathematics.Line2 Invert(Colossal.Mathematics.Line2 line);
    public static Colossal.Mathematics.Line2+Segment Invert(Colossal.Mathematics.Line2+Segment line);
    public static Colossal.Mathematics.Line3 Invert(Colossal.Mathematics.Line3 line);
    public static Colossal.Mathematics.Line3+Segment Invert(Colossal.Mathematics.Line3+Segment line);
    public static System.Boolean IsClockwise(Colossal.Mathematics.Triangle2 triangle);
    public static System.Boolean IsPowOf2(System.Int32 val);
    public static Colossal.Mathematics.Bezier4x3 Join(Colossal.Mathematics.Bezier4x3 input1, Colossal.Mathematics.Bezier4x3 input2);
    public static Unity.Mathematics.float2 Left(Unity.Mathematics.float2 forward);
    public static System.Single Length(Colossal.Mathematics.Bezier4x1 curve);
    public static System.Single Length(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1 t);
    public static System.Single Length(Colossal.Mathematics.Bezier4x2 curve);
    public static System.Single Length(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1 t);
    public static System.Single Length(Colossal.Mathematics.Bezier4x3 curve);
    public static System.Single Length(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1 t);
    public static System.Single Length(Colossal.Mathematics.Line1+Segment line);
    public static System.Single Length(Colossal.Mathematics.Line2+Segment line);
    public static System.Single Length(Colossal.Mathematics.Line3+Segment line);
    public static System.Single LengthSquared(Colossal.Mathematics.Line1+Segment line);
    public static System.Single LengthSquared(Colossal.Mathematics.Line2+Segment line);
    public static System.Single LengthSquared(Colossal.Mathematics.Line3+Segment line);
    public static Colossal.Mathematics.Bezier4x1 Lerp(Colossal.Mathematics.Bezier4x1 curve1, Colossal.Mathematics.Bezier4x1 curve2, System.Single t);
    public static Colossal.Mathematics.Bezier4x2 Lerp(Colossal.Mathematics.Bezier4x2 curve1, Colossal.Mathematics.Bezier4x2 curve2, System.Single t);
    public static Colossal.Mathematics.Bezier4x3 Lerp(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, System.Single t);
    public static Colossal.Mathematics.Bezier4x3 Lerp(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Colossal.Mathematics.Bezier4x1 t);
    public static Colossal.Mathematics.Bounds1 Lerp(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2, System.Single t);
    public static Colossal.Mathematics.Bounds3 Lerp(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, System.Single t);
    public static Colossal.Mathematics.Box3 Lerp(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.Box3 box2, System.Single t);
    public static Colossal.Mathematics.Line1 Lerp(Colossal.Mathematics.Line1 line1, Colossal.Mathematics.Line1 line2, System.Single t);
    public static Colossal.Mathematics.Line1+Segment Lerp(Colossal.Mathematics.Line1+Segment line1, Colossal.Mathematics.Line1+Segment line2, System.Single t);
    public static Colossal.Mathematics.Line2 Lerp(Colossal.Mathematics.Line2 line1, Colossal.Mathematics.Line2 line2, System.Single t);
    public static Colossal.Mathematics.Line2+Segment Lerp(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, System.Single t);
    public static Colossal.Mathematics.Line3 Lerp(Colossal.Mathematics.Line3 line1, Colossal.Mathematics.Line3 line2, System.Single t);
    public static Colossal.Mathematics.Line3+Segment Lerp(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, System.Single t);
    public static Colossal.Mathematics.Line3+Segment Line(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 t);
    public static Colossal.Mathematics.Line3+Segment Line(Colossal.Mathematics.Bezier4x3 curve);
    public static System.Int32 Log2(System.Int32 val);
    public static System.Single Logistic(System.Single a, System.Single c, System.Single k, System.Single x);
    public static System.Single Max(Colossal.Mathematics.Bezier4x1 curve);
    public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Bezier4x2 curve);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Bezier4x3 curve);
    public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Circle2 circle);
    public static System.Single Max(Colossal.Mathematics.Line1+Segment line);
    public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Line2+Segment line);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Line3+Segment line);
    public static System.Single Max(Unity.Mathematics.float2 value);
    public static System.Single Max(Unity.Mathematics.float3 value);
    public static System.Single Max(Unity.Mathematics.float4 value);
    public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Quad2 quad);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Quad3 quad);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Sphere3 sphere);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Tetrahedron3 tetrahedron);
    public static System.Single Max(Colossal.Mathematics.Triangle1 triangle);
    public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Triangle2 triangle);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Triangle3 triangle);
    public static Unity.Mathematics.float3 Max(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron);
    public static Unity.Mathematics.float2 MaxAbs(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
    public static System.Single MaxDot(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 direction, System.Single& t);
    public static System.Single Min(Colossal.Mathematics.Bezier4x1 curve);
    public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Bezier4x2 curve);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Bezier4x3 curve);
    public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Circle2 circle);
    public static System.Single Min(Colossal.Mathematics.Line1+Segment line);
    public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Line2+Segment line);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Line3+Segment line);
    public static System.Single Min(Unity.Mathematics.float2 value);
    public static System.Single Min(Unity.Mathematics.float3 value);
    public static System.Single Min(Unity.Mathematics.float4 value);
    public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Quad2 quad);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Quad3 quad);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Sphere3 sphere);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Tetrahedron3 tetrahedron);
    public static System.Single Min(Colossal.Mathematics.Triangle1 triangle);
    public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Triangle2 triangle);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Triangle3 triangle);
    public static Unity.Mathematics.float3 Min(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron);
    public static Unity.Mathematics.float3 NormalCCW(Colossal.Mathematics.Triangle3 triangle);
    public static Unity.Mathematics.float3 NormalCW(Colossal.Mathematics.Triangle3 triangle);
    public static Unity.Mathematics.float3 Normalize(Unity.Mathematics.float3 value1, Unity.Mathematics.float2 value2);
    public static System.UInt32 NormalToOctahedral(Unity.Mathematics.float3 n);
    public static System.Single Perimeter(Colossal.Mathematics.Triangle2 triangle);
    public static System.Single Perimeter(Colossal.Mathematics.Triangle3 triangle);
    public static System.Single Position(Colossal.Mathematics.Bezier4x1 curve, System.Single t);
    public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
    public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Bezier4x3 curve, System.Single t);
    public static System.Single Position(Colossal.Mathematics.Line1 line, System.Single t);
    public static System.Single Position(Colossal.Mathematics.Line1+Segment line, System.Single t);
    public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Line2 line, System.Single t);
    public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Line2+Segment line, System.Single t);
    public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Line3 line, System.Single t);
    public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Line3+Segment line, System.Single t);
    public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Tetrahedron3 tetrahedron, Unity.Mathematics.float3 t);
    public static System.Single Position(Colossal.Mathematics.Triangle1 triangle, Unity.Mathematics.float2 t);
    public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 t);
    public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.float2 t);
    private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
    private static System.Boolean QuadIntersectHelper(Unity.Mathematics.float4 x, Unity.Mathematics.float4 y, Unity.Mathematics.float2 position);
    private static System.Boolean QuadIntersectHelper(Unity.Mathematics.float4 x, Unity.Mathematics.float4 y, Unity.Mathematics.float2 p, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
    public static Unity.Mathematics.float3 Quantize(Unity.Mathematics.float3 v, Unity.Mathematics.float3 quant);
    private static System.Int32 QuantizeSnorm(System.Single v, System.Int32 N);
    public static Unity.Mathematics.float2 Right(Unity.Mathematics.float2 forward);
    public static Unity.Mathematics.float2 RotateLeft(Unity.Mathematics.float2 vector, System.Single angle);
    public static Unity.Mathematics.float2 RotateRight(Unity.Mathematics.float2 vector, System.Single angle);
    public static System.Single RotationAngle(Unity.Mathematics.float2 vector1, Unity.Mathematics.float2 vector2);
    public static System.Single RotationAngle(Unity.Mathematics.quaternion a, Unity.Mathematics.quaternion b);
    public static System.Single RotationAngle(System.Single fromAngle, System.Single toAngle);
    public static System.Single RotationAngleLeft(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
    public static System.Single RotationAngleRight(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
    public static System.Single RotationAngleSignedLeft(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
    public static System.Single RotationAngleSignedRight(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
    public static System.Int32 RoundToIntRandom(Unity.Mathematics.Random& random, System.Single value);
    public static Unity.Mathematics.int4 RoundToIntRandom(Unity.Mathematics.Random& random, Unity.Mathematics.float4 value);
    public static System.Single Size(Colossal.Mathematics.Bounds1 bounds);
    public static Unity.Mathematics.float2 Size(Colossal.Mathematics.Bounds2 bounds);
    public static Unity.Mathematics.float3 Size(Colossal.Mathematics.Bounds3 bounds);
    public static System.Single SmoothDamp(System.Single current, System.Single target, System.Single& currentVelocity, System.Single smoothTime, System.Single maxSpeed, System.Single deltaTime);
    public static System.Single Snap(System.Single value, System.Single interval);
    public static Unity.Mathematics.float2 Snap(Unity.Mathematics.float2 value, Unity.Mathematics.float2 interval);
    public static System.Single Snap(System.Single value, System.Single interval, System.Single offset);
    public static Unity.Mathematics.float2 Snap(Unity.Mathematics.float2 value, Unity.Mathematics.float2 interval, Unity.Mathematics.float2 offset);
    public static Colossal.Mathematics.Sphere3 Sphere(Colossal.Mathematics.Sphere3 sphere1, Colossal.Mathematics.Sphere3 sphere2);
    public static Colossal.Mathematics.Bezier4x3 StartReflect(Colossal.Mathematics.Bezier4x3 curve);
    public static System.Single StartTangent(Colossal.Mathematics.Bezier4x1 curve);
    public static Unity.Mathematics.float2 StartTangent(Colossal.Mathematics.Bezier4x2 curve);
    public static Unity.Mathematics.float3 StartTangent(Colossal.Mathematics.Bezier4x3 curve);
    public static System.Single Tangent(Colossal.Mathematics.Bezier4x1 curve, System.Single t);
    public static Unity.Mathematics.float2 Tangent(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
    public static Unity.Mathematics.float3 Tangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t);
    public static System.Single Tangent(Colossal.Mathematics.Line1 line);
    public static System.Single Tangent(Colossal.Mathematics.Line1+Segment line);
    public static Unity.Mathematics.float2 Tangent(Colossal.Mathematics.Line2 line);
    public static Unity.Mathematics.float2 Tangent(Colossal.Mathematics.Line2+Segment line);
    public static Unity.Mathematics.float3 Tangent(Colossal.Mathematics.Line3 line);
    public static Unity.Mathematics.float3 Tangent(Colossal.Mathematics.Line3+Segment line);
    public static System.UInt32 TangentToOctahedral(Unity.Mathematics.float4 t);
    public static Colossal.Mathematics.Bounds2 TightBounds(Colossal.Mathematics.Bezier4x2 curve);
    public static Colossal.Mathematics.Bounds3 TightBounds(Colossal.Mathematics.Bezier4x3 curve);
    private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 pos1, Unity.Mathematics.float3 pos2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Tetrahedron3 tetrahedron1, Unity.Mathematics.float3 pos1, Unity.Mathematics.float3 pos2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Void TriangleIntersectAddFirstEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, System.Single startT, System.Single endT, Colossal.Mathematics.Bounds2 bounds);
    private static System.Void TriangleIntersectAddNextEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, System.Single startT, System.Single endT, Colossal.Mathematics.Bounds2 bounds, System.Single& area);
    private static System.Void TriangleIntersectCheckLastEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Colossal.Mathematics.Bounds2 bounds, System.Single& area);
    private static System.Boolean TriangleIntersectHelper(Unity.Mathematics.float3 x, Unity.Mathematics.float3 y, Unity.Mathematics.float2 position);
    public static System.Boolean TryNormalize(Unity.Mathematics.float2& value);
    public static System.Boolean TryNormalize(Unity.Mathematics.float3& value);
    public static System.Boolean TryNormalize(Unity.Mathematics.float2& value, System.Single newLength);
    public static System.Boolean TryNormalize(Unity.Mathematics.float3& value, System.Single newLength);
}
```


## Methods

- `public static Acceleration(Colossal.Mathematics.Bezier4x1 curve, System.Single t) : System.Single`  

```csharp
public static System.Single Acceleration(Colossal.Mathematics.Bezier4x1 curve, System.Single t);
```

- `public static Acceleration(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Acceleration(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
```

- `public static Acceleration(Colossal.Mathematics.Bezier4x3 curve, System.Single t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Acceleration(Colossal.Mathematics.Bezier4x3 curve, System.Single t);
```

- `public static Area(Colossal.Mathematics.Bounds2 bounds) : System.Single`  

```csharp
public static System.Single Area(Colossal.Mathematics.Bounds2 bounds);
```

- `public static Area(Colossal.Mathematics.Bounds3 bounds) : System.Single`  

```csharp
public static System.Single Area(Colossal.Mathematics.Bounds3 bounds);
```

- `public static Area(Colossal.Mathematics.Triangle2 triangle) : System.Single`  

```csharp
public static System.Single Area(Colossal.Mathematics.Triangle2 triangle);
```

- `public static Area(Colossal.Mathematics.Triangle3 triangle) : System.Single`  

```csharp
public static System.Single Area(Colossal.Mathematics.Triangle3 triangle);
```

- `public static AxisAngle(Unity.Mathematics.quaternion q, Unity.Mathematics.float3& axis, System.Single& angle) : System.Void`  

```csharp
public static System.Void AxisAngle(Unity.Mathematics.quaternion q, Unity.Mathematics.float3& axis, System.Single& angle);
```

- `public static Bounds(Colossal.Mathematics.Bezier4x1 curve) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Bounds(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static Bounds(Colossal.Mathematics.Bezier4x2 curve) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static Bounds(Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Bounds(System.Single a, System.Single b) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Bounds(System.Single a, System.Single b);
```

- `public static Bounds(Unity.Mathematics.float2 positions) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Bounds(Unity.Mathematics.float2 positions);
```

- `public static Bounds(Colossal.Mathematics.Line1+Segment line) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Bounds(Colossal.Mathematics.Line1+Segment line);
```

- `public static Bounds(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Bounds(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
```

- `public static Bounds(Colossal.Mathematics.Line2+Segment line) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Line2+Segment line);
```

- `public static Bounds(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b);
```

- `public static Bounds(Colossal.Mathematics.Line3+Segment line) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Line3+Segment line);
```

- `public static Bounds(Colossal.Mathematics.Box3 box) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Box3 box);
```

- `public static Bounds(Colossal.Mathematics.Circle2 circle) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Circle2 circle);
```

- `public static Bounds(Colossal.Mathematics.Quad2 quad) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Quad2 quad);
```

- `public static Bounds(Colossal.Mathematics.Quad3 quad) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Quad3 quad);
```

- `public static Bounds(Colossal.Mathematics.Sphere3 sphere) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Sphere3 sphere);
```

- `public static Bounds(Colossal.Mathematics.Tetrahedron3 tetrahedron) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Tetrahedron3 tetrahedron);
```

- `public static Bounds(Colossal.Mathematics.Triangle1 triangle) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Bounds(Colossal.Mathematics.Triangle1 triangle);
```

- `public static Bounds(Colossal.Mathematics.Triangle2 triangle) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Bounds(Colossal.Mathematics.Triangle2 triangle);
```

- `public static Bounds(Colossal.Mathematics.Triangle3 triangle) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.Triangle3 triangle);
```

- `public static Bounds(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Bounds(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron);
```

- `public static Box(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position) : Colossal.Mathematics.Box3`  

```csharp
public static Colossal.Mathematics.Box3 Box(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 position);
```

- `private static BoxIntersectHelper(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, Unity.Mathematics.quaternion rotate2to1, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean BoxIntersectHelper(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, Unity.Mathematics.quaternion rotate2to1, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static BoxIntersectHelper(Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean BoxIntersectHelper(Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static Center(Colossal.Mathematics.Bounds1 bounds) : System.Single`  

```csharp
public static System.Single Center(Colossal.Mathematics.Bounds1 bounds);
```

- `public static Center(Colossal.Mathematics.Bounds2 bounds) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Center(Colossal.Mathematics.Bounds2 bounds);
```

- `public static Center(Colossal.Mathematics.Bounds3 bounds) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Center(Colossal.Mathematics.Bounds3 bounds);
```

- `public static Center(Colossal.Mathematics.Quad2 quad) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Center(Colossal.Mathematics.Quad2 quad);
```

- `public static Clamp(System.Single position, Colossal.Mathematics.Bounds1 bounds) : System.Single`  

```csharp
public static System.Single Clamp(System.Single position, Colossal.Mathematics.Bounds1 bounds);
```

- `public static Clamp(Unity.Mathematics.float2 position, Colossal.Mathematics.Bounds2 bounds) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Clamp(Unity.Mathematics.float2 position, Colossal.Mathematics.Bounds2 bounds);
```

- `public static Clamp(Unity.Mathematics.float3 position, Colossal.Mathematics.Bounds3 bounds) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Clamp(Unity.Mathematics.float3 position, Colossal.Mathematics.Bounds3 bounds);
```

- `public static ClampLength(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single length) : System.Boolean`  

```csharp
public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
```

- `public static ClampLength(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single& length) : System.Boolean`  

```csharp
public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
```

- `public static ClampLength(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single length) : System.Boolean`  

```csharp
public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
```

- `public static ClampLength(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single& length) : System.Boolean`  

```csharp
public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
```

- `public static ClampLength(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single length) : System.Boolean`  

```csharp
public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
```

- `public static ClampLength(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single& length) : System.Boolean`  

```csharp
public static System.Boolean ClampLength(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
```

- `public static ClampLength(Unity.Mathematics.float2 value, System.Single maxLength) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 ClampLength(Unity.Mathematics.float2 value, System.Single maxLength);
```

- `public static ClampLength(Unity.Mathematics.float3 value, System.Single maxLength) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ClampLength(Unity.Mathematics.float3 value, System.Single maxLength);
```

- `public static ClampLengthInverse(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single length) : System.Boolean`  

```csharp
public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
```

- `public static ClampLengthInverse(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single& length) : System.Boolean`  

```csharp
public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
```

- `public static ClampLengthInverse(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single length) : System.Boolean`  

```csharp
public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
```

- `public static ClampLengthInverse(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single& length) : System.Boolean`  

```csharp
public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
```

- `public static ClampLengthInverse(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single length) : System.Boolean`  

```csharp
public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single length);
```

- `public static ClampLengthInverse(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single& length) : System.Boolean`  

```csharp
public static System.Boolean ClampLengthInverse(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1& t, System.Single& length);
```

- `public static Clockwise(Colossal.Mathematics.Triangle2 triangle) : Colossal.Mathematics.Triangle2`  

```csharp
public static Colossal.Mathematics.Triangle2 Clockwise(Colossal.Mathematics.Triangle2 triangle);
```

- `public static Curvature(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : System.Single`  

```csharp
public static System.Single Curvature(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
```

- `public static Cut(Colossal.Mathematics.Bezier4x1 curve, Unity.Mathematics.float2 t) : Colossal.Mathematics.Bezier4x1`  

```csharp
public static Colossal.Mathematics.Bezier4x1 Cut(Colossal.Mathematics.Bezier4x1 curve, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 t) : Colossal.Mathematics.Bezier4x2`  

```csharp
public static Colossal.Mathematics.Bezier4x2 Cut(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 t) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 Cut(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1 bounds) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 Cut(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1 bounds);
```

- `public static Cut(Colossal.Mathematics.Line1 line, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line1+Segment`  

```csharp
public static Colossal.Mathematics.Line1+Segment Cut(Colossal.Mathematics.Line1 line, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Line1+Segment line, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line1+Segment`  

```csharp
public static Colossal.Mathematics.Line1+Segment Cut(Colossal.Mathematics.Line1+Segment line, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Line2 line, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line2+Segment`  

```csharp
public static Colossal.Mathematics.Line2+Segment Cut(Colossal.Mathematics.Line2 line, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line2+Segment`  

```csharp
public static Colossal.Mathematics.Line2+Segment Cut(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Line3 line, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment Cut(Colossal.Mathematics.Line3 line, Unity.Mathematics.float2 t);
```

- `public static Cut(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment Cut(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2 t);
```

- `private static CylinderBoxIntersectHelper(Colossal.Mathematics.Bounds3 rectBounds, Colossal.Mathematics.Bounds1 cylinderHeight, Colossal.Mathematics.Circle2 cylinderCircle, Unity.Mathematics.quaternion rotateBtoC, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection) : System.Boolean`  

```csharp
private static System.Boolean CylinderBoxIntersectHelper(Colossal.Mathematics.Bounds3 rectBounds, Colossal.Mathematics.Bounds1 cylinderHeight, Colossal.Mathematics.Circle2 cylinderCircle, Unity.Mathematics.quaternion rotateBtoC, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
```

- `private static CylinderBoxIntersectHelper(Colossal.Mathematics.Bounds1 height, Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection) : System.Boolean`  

```csharp
private static System.Boolean CylinderBoxIntersectHelper(Colossal.Mathematics.Bounds1 height, Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
```

- `private static CylinderBoxIntersectHelper(System.Single height, Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 c1, Unity.Mathematics.float3 d1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Unity.Mathematics.float3 c2, Unity.Mathematics.float3 d2, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection) : System.Boolean`  

```csharp
private static System.Boolean CylinderBoxIntersectHelper(System.Single height, Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 c1, Unity.Mathematics.float3 d1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Unity.Mathematics.float3 c2, Unity.Mathematics.float3 d2, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
```

- `private static CylinderBoxIntersectHelper2(Colossal.Mathematics.Bounds3 boxBounds, Colossal.Mathematics.Bounds1 cylinderHeight, Colossal.Mathematics.Circle2 cylinderCircle, Unity.Mathematics.quaternion rotateCtoB, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection) : System.Boolean`  

```csharp
private static System.Boolean CylinderBoxIntersectHelper2(Colossal.Mathematics.Bounds3 boxBounds, Colossal.Mathematics.Bounds1 cylinderHeight, Colossal.Mathematics.Circle2 cylinderCircle, Unity.Mathematics.quaternion rotateCtoB, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
```

- `public static Determinant(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b) : System.Single`  

```csharp
public static System.Single Determinant(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
```

- `public static Determinant(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c) : System.Single`  

```csharp
public static System.Single Determinant(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c);
```

- `private static DifferentSide(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Colossal.Mathematics.Line2 line) : System.Boolean`  

```csharp
private static System.Boolean DifferentSide(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Colossal.Mathematics.Line2 line);
```

- `public static Distance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 position, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.float2 range, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.float2 range, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t);
```

- `public static Distance(Colossal.Mathematics.Bounds1 bounds, System.Single position) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bounds1 bounds, System.Single position);
```

- `public static Distance(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position);
```

- `public static Distance(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2);
```

- `public static Distance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position);
```

- `public static Distance(Colossal.Mathematics.Line2 line, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line2 line, Unity.Mathematics.float2 position, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 position, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, Unity.Mathematics.float2& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, Unity.Mathematics.float2& t);
```

- `public static Distance(Colossal.Mathematics.Line3 line, Unity.Mathematics.float3 position, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line3 line, Unity.Mathematics.float3 position, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3 position, System.Single& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3 position, System.Single& t);
```

- `public static Distance(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Mathematics.float2& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Mathematics.float2& t);
```

- `public static Distance(Colossal.Mathematics.Line3 line1, Colossal.Mathematics.Line3 line2, Unity.Mathematics.float2& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Line3 line1, Colossal.Mathematics.Line3 line2, Unity.Mathematics.float2& t);
```

- `public static Distance(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Unity.Mathematics.float2& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Unity.Mathematics.float2& t);
```

- `public static Distance(Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.float3 position, Unity.Mathematics.float2& t) : System.Single`  

```csharp
public static System.Single Distance(Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.float3 position, Unity.Mathematics.float2& t);
```

- `public static DistanceSquared(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& t) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& t);
```

- `public static DistanceSquared(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.float2 range, System.Single& t) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, Unity.Mathematics.float2 range, System.Single& t);
```

- `public static DistanceSquared(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position);
```

- `public static DistanceSquared(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2);
```

- `public static DistanceSquared(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position);
```

- `public static DistanceSquared(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 position, System.Single& t) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2 position, System.Single& t);
```

- `public static DistanceSquared(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3 position, System.Single& t) : System.Single`  

```csharp
public static System.Single DistanceSquared(Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3 position, System.Single& t);
```

- `public static Divide(Colossal.Mathematics.Bezier4x1 input, Colossal.Mathematics.Bezier4x1& output1, Colossal.Mathematics.Bezier4x1& output2, System.Single t) : System.Void`  

```csharp
public static System.Void Divide(Colossal.Mathematics.Bezier4x1 input, Colossal.Mathematics.Bezier4x1& output1, Colossal.Mathematics.Bezier4x1& output2, System.Single t);
```

- `public static Divide(Colossal.Mathematics.Bezier4x2 input, Colossal.Mathematics.Bezier4x2& output1, Colossal.Mathematics.Bezier4x2& output2, System.Single t) : System.Void`  

```csharp
public static System.Void Divide(Colossal.Mathematics.Bezier4x2 input, Colossal.Mathematics.Bezier4x2& output1, Colossal.Mathematics.Bezier4x2& output2, System.Single t);
```

- `public static Divide(Colossal.Mathematics.Bezier4x3 input, Colossal.Mathematics.Bezier4x3& output1, Colossal.Mathematics.Bezier4x3& output2, System.Single t) : System.Void`  

```csharp
public static System.Void Divide(Colossal.Mathematics.Bezier4x3 input, Colossal.Mathematics.Bezier4x3& output1, Colossal.Mathematics.Bezier4x3& output2, System.Single t);
```

- `public static EncodeOctahedral(Unity.Mathematics.float3 n) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 EncodeOctahedral(Unity.Mathematics.float3 n);
```

- `public static EndReflect(Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 EndReflect(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static EndTangent(Colossal.Mathematics.Bezier4x1 curve) : System.Single`  

```csharp
public static System.Single EndTangent(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static EndTangent(Colossal.Mathematics.Bezier4x2 curve) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 EndTangent(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static EndTangent(Colossal.Mathematics.Bezier4x3 curve) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 EndTangent(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Expand(Colossal.Mathematics.Bounds1 bounds, System.Single range) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Expand(Colossal.Mathematics.Bounds1 bounds, System.Single range);
```

- `public static Expand(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 range) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 Expand(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 range);
```

- `public static Expand(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 range) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Expand(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 range);
```

- `public static Expand(Colossal.Mathematics.Quad2 quad, System.Single t) : Colossal.Mathematics.Quad2`  

```csharp
public static Colossal.Mathematics.Quad2 Expand(Colossal.Mathematics.Quad2 quad, System.Single t);
```

- `public static Extents(Colossal.Mathematics.Bounds1 bounds) : System.Single`  

```csharp
public static System.Single Extents(Colossal.Mathematics.Bounds1 bounds);
```

- `public static Extents(Colossal.Mathematics.Bounds2 bounds) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Extents(Colossal.Mathematics.Bounds2 bounds);
```

- `public static Extents(Colossal.Mathematics.Bounds3 bounds) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Extents(Colossal.Mathematics.Bounds3 bounds);
```

- `public static Incenter(Colossal.Mathematics.Triangle1 triangle, System.Single& radius) : System.Single`  

```csharp
public static System.Single Incenter(Colossal.Mathematics.Triangle1 triangle, System.Single& radius);
```

- `public static Incenter(Colossal.Mathematics.Triangle2 triangle, System.Single& radius) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Incenter(Colossal.Mathematics.Triangle2 triangle, System.Single& radius);
```

- `public static Incenter(Colossal.Mathematics.Triangle3 triangle, System.Single& radius) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Incenter(Colossal.Mathematics.Triangle3 triangle, System.Single& radius);
```

- `public static Intersect(Colossal.Mathematics.Bezier4x1 curve, System.Single position, System.Single& t, System.Int32 iterations) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bezier4x1 curve, System.Single position, System.Single& t, System.Int32 iterations);
```

- `public static Intersect(Colossal.Mathematics.Bezier4x2 curve1, Colossal.Mathematics.Bezier4x2 curve2, Unity.Mathematics.float2& t, System.Int32 iterations) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bezier4x2 curve1, Colossal.Mathematics.Bezier4x2 curve2, Unity.Mathematics.float2& t, System.Int32 iterations);
```

- `public static Intersect(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t, System.Int32 iterations) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t, System.Int32 iterations);
```

- `public static Intersect(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2);
```

- `public static Intersect(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2, Colossal.Mathematics.Bounds1& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2, Colossal.Mathematics.Bounds1& intersection);
```

- `public static Intersect(Colossal.Mathematics.Bounds1 bounds, System.Single position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds, System.Single position);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds1, Colossal.Mathematics.Bounds2 bounds2, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Unity.Mathematics.float2 position);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Circle2 circle) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Circle2 circle);
```

- `public static Intersect(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2);
```

- `public static Intersect(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float3 position);
```

- `public static Intersect(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static Intersect(Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float2 position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle, Unity.Mathematics.float2 position);
```

- `public static Intersect(Colossal.Mathematics.Circle2 circle1, Colossal.Mathematics.Circle2 circle2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle1, Colossal.Mathematics.Circle2 circle2);
```

- `public static Intersect(Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Cylinder3 cylinder, Colossal.Mathematics.Box3 box, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Cylinder3 cylinder, Colossal.Mathematics.Box3 box, Colossal.Mathematics.Bounds3& cylinderIntersection, Colossal.Mathematics.Bounds3& boxIntersection);
```

- `public static Intersect(Colossal.Mathematics.Line1 line, System.Single position, System.Single& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Line1 line, System.Single position, System.Single& t);
```

- `public static Intersect(Colossal.Mathematics.Line1+Segment line, System.Single position, System.Single& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Line1+Segment line, System.Single position, System.Single& t);
```

- `public static Intersect(Colossal.Mathematics.Bounds1 bounds, Colossal.Mathematics.Line1+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds1 bounds, Colossal.Mathematics.Line1+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Line2 line1, Colossal.Mathematics.Line2 line2, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Line2 line1, Colossal.Mathematics.Line2 line2, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2 line2, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2 line2, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad, Unity.Mathematics.float2 position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Unity.Mathematics.float2 position);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Quad2 quad) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Quad2 quad);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad1, Colossal.Mathematics.Quad2 quad2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad1, Colossal.Mathematics.Quad2 quad2);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Triangle2 triangle) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Triangle2 triangle);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Circle2 circle) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Circle2 circle);
```

- `public static Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Circle2 circle, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Quad2 quad, System.Single& area) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Quad2 quad, System.Single& area);
```

- `public static Intersect(Colossal.Mathematics.Quad3 quad, Colossal.Mathematics.Line3 line, System.Single& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad3 quad, Colossal.Mathematics.Line3 line, System.Single& t);
```

- `public static Intersect(Colossal.Mathematics.Quad3 quad, Colossal.Mathematics.Line3+Segment line, System.Single& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Quad3 quad, Colossal.Mathematics.Line3+Segment line, System.Single& t);
```

- `public static Intersect(Colossal.Mathematics.Sphere3 sphere, Unity.Mathematics.float3 position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere, Unity.Mathematics.float3 position);
```

- `public static Intersect(Colossal.Mathematics.Sphere3 sphere1, Colossal.Mathematics.Sphere3 sphere2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere1, Colossal.Mathematics.Sphere3 sphere2);
```

- `public static Intersect(Colossal.Mathematics.Sphere3 sphere, Colossal.Mathematics.Line3 line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere, Colossal.Mathematics.Line3 line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Sphere3 sphere, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Sphere3 sphere, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Tetrahedron3 tetrahedron, Unity.Mathematics.float3 position, Unity.Mathematics.float3& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Tetrahedron3 tetrahedron, Unity.Mathematics.float3 position, Unity.Mathematics.float3& t);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Triangle2 triangle) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Triangle2 triangle);
```

- `public static Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Triangle2 triangle, System.Single& area) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Bounds2 bounds, Colossal.Mathematics.Triangle2 triangle, System.Single& area);
```

- `public static Intersect(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 position);
```

- `public static Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Line2 line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
```

- `public static Intersect(Colossal.Mathematics.Triangle2 triangle1, Colossal.Mathematics.Triangle2 triangle2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle1, Colossal.Mathematics.Triangle2 triangle2);
```

- `public static Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Circle2 circle) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle2 triangle, Colossal.Mathematics.Circle2 circle);
```

- `public static Intersect(Colossal.Mathematics.Triangle3 triangle, Colossal.Mathematics.Line3 line, Unity.Mathematics.float3& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle3 triangle, Colossal.Mathematics.Line3 line, Unity.Mathematics.float3& t);
```

- `public static Intersect(Colossal.Mathematics.Triangle3 triangle, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3& t) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Triangle3 triangle, Colossal.Mathematics.Line3+Segment line, Unity.Mathematics.float3& t);
```

- `public static Intersect(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static IntPow(System.Int32 b, System.Int32 exp) : System.Int32`  

```csharp
public static System.Int32 IntPow(System.Int32 b, System.Int32 exp);
```

- `public static InverseSmoothStep(System.Single a, System.Single b, System.Single x) : System.Single`  

```csharp
public static System.Single InverseSmoothStep(System.Single a, System.Single b, System.Single x);
```

- `public static InverseSmoothStep(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, Unity.Mathematics.float2 x) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 InverseSmoothStep(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, Unity.Mathematics.float2 x);
```

- `public static InverseSmoothStep(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 x) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 InverseSmoothStep(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 x);
```

- `public static InverseSmoothStep(Unity.Mathematics.float4 a, Unity.Mathematics.float4 b, Unity.Mathematics.float4 x) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 InverseSmoothStep(Unity.Mathematics.float4 a, Unity.Mathematics.float4 b, Unity.Mathematics.float4 x);
```

- `public static Invert(Colossal.Mathematics.Bezier4x1 curve) : Colossal.Mathematics.Bezier4x1`  

```csharp
public static Colossal.Mathematics.Bezier4x1 Invert(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static Invert(Colossal.Mathematics.Bezier4x2 curve) : Colossal.Mathematics.Bezier4x2`  

```csharp
public static Colossal.Mathematics.Bezier4x2 Invert(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static Invert(Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 Invert(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Invert(Colossal.Mathematics.Bounds1 bounds) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Invert(Colossal.Mathematics.Bounds1 bounds);
```

- `public static Invert(Colossal.Mathematics.Line1 line) : Colossal.Mathematics.Line1`  

```csharp
public static Colossal.Mathematics.Line1 Invert(Colossal.Mathematics.Line1 line);
```

- `public static Invert(Colossal.Mathematics.Line1+Segment line) : Colossal.Mathematics.Line1+Segment`  

```csharp
public static Colossal.Mathematics.Line1+Segment Invert(Colossal.Mathematics.Line1+Segment line);
```

- `public static Invert(Colossal.Mathematics.Line2 line) : Colossal.Mathematics.Line2`  

```csharp
public static Colossal.Mathematics.Line2 Invert(Colossal.Mathematics.Line2 line);
```

- `public static Invert(Colossal.Mathematics.Line2+Segment line) : Colossal.Mathematics.Line2+Segment`  

```csharp
public static Colossal.Mathematics.Line2+Segment Invert(Colossal.Mathematics.Line2+Segment line);
```

- `public static Invert(Colossal.Mathematics.Line3 line) : Colossal.Mathematics.Line3`  

```csharp
public static Colossal.Mathematics.Line3 Invert(Colossal.Mathematics.Line3 line);
```

- `public static Invert(Colossal.Mathematics.Line3+Segment line) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment Invert(Colossal.Mathematics.Line3+Segment line);
```

- `public static IsClockwise(Colossal.Mathematics.Triangle2 triangle) : System.Boolean`  

```csharp
public static System.Boolean IsClockwise(Colossal.Mathematics.Triangle2 triangle);
```

- `public static IsPowOf2(System.Int32 val) : System.Boolean`  

```csharp
public static System.Boolean IsPowOf2(System.Int32 val);
```

- `public static Join(Colossal.Mathematics.Bezier4x3 input1, Colossal.Mathematics.Bezier4x3 input2) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 Join(Colossal.Mathematics.Bezier4x3 input1, Colossal.Mathematics.Bezier4x3 input2);
```

- `public static Left(Unity.Mathematics.float2 forward) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Left(Unity.Mathematics.float2 forward);
```

- `public static Length(Colossal.Mathematics.Bezier4x1 curve) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static Length(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1 t) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Bezier4x1 curve, Colossal.Mathematics.Bounds1 t);
```

- `public static Length(Colossal.Mathematics.Bezier4x2 curve) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static Length(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1 t) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Bezier4x2 curve, Colossal.Mathematics.Bounds1 t);
```

- `public static Length(Colossal.Mathematics.Bezier4x3 curve) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Length(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1 t) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Bezier4x3 curve, Colossal.Mathematics.Bounds1 t);
```

- `public static Length(Colossal.Mathematics.Line1+Segment line) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Line1+Segment line);
```

- `public static Length(Colossal.Mathematics.Line2+Segment line) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Line2+Segment line);
```

- `public static Length(Colossal.Mathematics.Line3+Segment line) : System.Single`  

```csharp
public static System.Single Length(Colossal.Mathematics.Line3+Segment line);
```

- `public static LengthSquared(Colossal.Mathematics.Line1+Segment line) : System.Single`  

```csharp
public static System.Single LengthSquared(Colossal.Mathematics.Line1+Segment line);
```

- `public static LengthSquared(Colossal.Mathematics.Line2+Segment line) : System.Single`  

```csharp
public static System.Single LengthSquared(Colossal.Mathematics.Line2+Segment line);
```

- `public static LengthSquared(Colossal.Mathematics.Line3+Segment line) : System.Single`  

```csharp
public static System.Single LengthSquared(Colossal.Mathematics.Line3+Segment line);
```

- `public static Lerp(Colossal.Mathematics.Bezier4x1 curve1, Colossal.Mathematics.Bezier4x1 curve2, System.Single t) : Colossal.Mathematics.Bezier4x1`  

```csharp
public static Colossal.Mathematics.Bezier4x1 Lerp(Colossal.Mathematics.Bezier4x1 curve1, Colossal.Mathematics.Bezier4x1 curve2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Bezier4x2 curve1, Colossal.Mathematics.Bezier4x2 curve2, System.Single t) : Colossal.Mathematics.Bezier4x2`  

```csharp
public static Colossal.Mathematics.Bezier4x2 Lerp(Colossal.Mathematics.Bezier4x2 curve1, Colossal.Mathematics.Bezier4x2 curve2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, System.Single t) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 Lerp(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Colossal.Mathematics.Bezier4x1 t) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 Lerp(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Colossal.Mathematics.Bezier4x1 t);
```

- `public static Lerp(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2, System.Single t) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 Lerp(Colossal.Mathematics.Bounds1 bounds1, Colossal.Mathematics.Bounds1 bounds2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, System.Single t) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 Lerp(Colossal.Mathematics.Bounds3 bounds1, Colossal.Mathematics.Bounds3 bounds2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.Box3 box2, System.Single t) : Colossal.Mathematics.Box3`  

```csharp
public static Colossal.Mathematics.Box3 Lerp(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.Box3 box2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Line1 line1, Colossal.Mathematics.Line1 line2, System.Single t) : Colossal.Mathematics.Line1`  

```csharp
public static Colossal.Mathematics.Line1 Lerp(Colossal.Mathematics.Line1 line1, Colossal.Mathematics.Line1 line2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Line1+Segment line1, Colossal.Mathematics.Line1+Segment line2, System.Single t) : Colossal.Mathematics.Line1+Segment`  

```csharp
public static Colossal.Mathematics.Line1+Segment Lerp(Colossal.Mathematics.Line1+Segment line1, Colossal.Mathematics.Line1+Segment line2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Line2 line1, Colossal.Mathematics.Line2 line2, System.Single t) : Colossal.Mathematics.Line2`  

```csharp
public static Colossal.Mathematics.Line2 Lerp(Colossal.Mathematics.Line2 line1, Colossal.Mathematics.Line2 line2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, System.Single t) : Colossal.Mathematics.Line2+Segment`  

```csharp
public static Colossal.Mathematics.Line2+Segment Lerp(Colossal.Mathematics.Line2+Segment line1, Colossal.Mathematics.Line2+Segment line2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Line3 line1, Colossal.Mathematics.Line3 line2, System.Single t) : Colossal.Mathematics.Line3`  

```csharp
public static Colossal.Mathematics.Line3 Lerp(Colossal.Mathematics.Line3 line1, Colossal.Mathematics.Line3 line2, System.Single t);
```

- `public static Lerp(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, System.Single t) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment Lerp(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, System.Single t);
```

- `public static Line(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 t) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment Line(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2 t);
```

- `public static Line(Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Colossal.Mathematics.Line3+Segment Line(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Log2(System.Int32 val) : System.Int32`  

```csharp
public static System.Int32 Log2(System.Int32 val);
```

- `public static Logistic(System.Single a, System.Single c, System.Single k, System.Single x) : System.Single`  

```csharp
public static System.Single Logistic(System.Single a, System.Single c, System.Single k, System.Single x);
```

- `public static Max(Colossal.Mathematics.Bezier4x1 curve) : System.Single`  

```csharp
public static System.Single Max(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static Max(Colossal.Mathematics.Bezier4x2 curve) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static Max(Colossal.Mathematics.Bezier4x3 curve) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Max(Colossal.Mathematics.Circle2 circle) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Circle2 circle);
```

- `public static Max(Colossal.Mathematics.Line1+Segment line) : System.Single`  

```csharp
public static System.Single Max(Colossal.Mathematics.Line1+Segment line);
```

- `public static Max(Colossal.Mathematics.Line2+Segment line) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Line2+Segment line);
```

- `public static Max(Colossal.Mathematics.Line3+Segment line) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Line3+Segment line);
```

- `public static Max(Unity.Mathematics.float2 value) : System.Single`  

```csharp
public static System.Single Max(Unity.Mathematics.float2 value);
```

- `public static Max(Unity.Mathematics.float3 value) : System.Single`  

```csharp
public static System.Single Max(Unity.Mathematics.float3 value);
```

- `public static Max(Unity.Mathematics.float4 value) : System.Single`  

```csharp
public static System.Single Max(Unity.Mathematics.float4 value);
```

- `public static Max(Colossal.Mathematics.Quad2 quad) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Quad2 quad);
```

- `public static Max(Colossal.Mathematics.Quad3 quad) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Quad3 quad);
```

- `public static Max(Colossal.Mathematics.Sphere3 sphere) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Sphere3 sphere);
```

- `public static Max(Colossal.Mathematics.Tetrahedron3 tetrahedron) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Tetrahedron3 tetrahedron);
```

- `public static Max(Colossal.Mathematics.Triangle1 triangle) : System.Single`  

```csharp
public static System.Single Max(Colossal.Mathematics.Triangle1 triangle);
```

- `public static Max(Colossal.Mathematics.Triangle2 triangle) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Max(Colossal.Mathematics.Triangle2 triangle);
```

- `public static Max(Colossal.Mathematics.Triangle3 triangle) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.Triangle3 triangle);
```

- `public static Max(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Max(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron);
```

- `public static MaxAbs(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 MaxAbs(Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
```

- `public static MaxDot(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 direction, System.Single& t) : System.Single`  

```csharp
public static System.Single MaxDot(Colossal.Mathematics.Bezier4x2 curve, Unity.Mathematics.float2 direction, System.Single& t);
```

- `public static Min(Colossal.Mathematics.Bezier4x1 curve) : System.Single`  

```csharp
public static System.Single Min(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static Min(Colossal.Mathematics.Bezier4x2 curve) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static Min(Colossal.Mathematics.Bezier4x3 curve) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Min(Colossal.Mathematics.Circle2 circle) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Circle2 circle);
```

- `public static Min(Colossal.Mathematics.Line1+Segment line) : System.Single`  

```csharp
public static System.Single Min(Colossal.Mathematics.Line1+Segment line);
```

- `public static Min(Colossal.Mathematics.Line2+Segment line) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Line2+Segment line);
```

- `public static Min(Colossal.Mathematics.Line3+Segment line) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Line3+Segment line);
```

- `public static Min(Unity.Mathematics.float2 value) : System.Single`  

```csharp
public static System.Single Min(Unity.Mathematics.float2 value);
```

- `public static Min(Unity.Mathematics.float3 value) : System.Single`  

```csharp
public static System.Single Min(Unity.Mathematics.float3 value);
```

- `public static Min(Unity.Mathematics.float4 value) : System.Single`  

```csharp
public static System.Single Min(Unity.Mathematics.float4 value);
```

- `public static Min(Colossal.Mathematics.Quad2 quad) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Quad2 quad);
```

- `public static Min(Colossal.Mathematics.Quad3 quad) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Quad3 quad);
```

- `public static Min(Colossal.Mathematics.Sphere3 sphere) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Sphere3 sphere);
```

- `public static Min(Colossal.Mathematics.Tetrahedron3 tetrahedron) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Tetrahedron3 tetrahedron);
```

- `public static Min(Colossal.Mathematics.Triangle1 triangle) : System.Single`  

```csharp
public static System.Single Min(Colossal.Mathematics.Triangle1 triangle);
```

- `public static Min(Colossal.Mathematics.Triangle2 triangle) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Min(Colossal.Mathematics.Triangle2 triangle);
```

- `public static Min(Colossal.Mathematics.Triangle3 triangle) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.Triangle3 triangle);
```

- `public static Min(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Min(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron);
```

- `public static NormalCCW(Colossal.Mathematics.Triangle3 triangle) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 NormalCCW(Colossal.Mathematics.Triangle3 triangle);
```

- `public static NormalCW(Colossal.Mathematics.Triangle3 triangle) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 NormalCW(Colossal.Mathematics.Triangle3 triangle);
```

- `public static Normalize(Unity.Mathematics.float3 value1, Unity.Mathematics.float2 value2) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Normalize(Unity.Mathematics.float3 value1, Unity.Mathematics.float2 value2);
```

- `public static NormalToOctahedral(Unity.Mathematics.float3 n) : System.UInt32`  

```csharp
public static System.UInt32 NormalToOctahedral(Unity.Mathematics.float3 n);
```

- `public static Perimeter(Colossal.Mathematics.Triangle2 triangle) : System.Single`  

```csharp
public static System.Single Perimeter(Colossal.Mathematics.Triangle2 triangle);
```

- `public static Perimeter(Colossal.Mathematics.Triangle3 triangle) : System.Single`  

```csharp
public static System.Single Perimeter(Colossal.Mathematics.Triangle3 triangle);
```

- `public static Position(Colossal.Mathematics.Bezier4x1 curve, System.Single t) : System.Single`  

```csharp
public static System.Single Position(Colossal.Mathematics.Bezier4x1 curve, System.Single t);
```

- `public static Position(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
```

- `public static Position(Colossal.Mathematics.Bezier4x3 curve, System.Single t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Bezier4x3 curve, System.Single t);
```

- `public static Position(Colossal.Mathematics.Line1 line, System.Single t) : System.Single`  

```csharp
public static System.Single Position(Colossal.Mathematics.Line1 line, System.Single t);
```

- `public static Position(Colossal.Mathematics.Line1+Segment line, System.Single t) : System.Single`  

```csharp
public static System.Single Position(Colossal.Mathematics.Line1+Segment line, System.Single t);
```

- `public static Position(Colossal.Mathematics.Line2 line, System.Single t) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Line2 line, System.Single t);
```

- `public static Position(Colossal.Mathematics.Line2+Segment line, System.Single t) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Line2+Segment line, System.Single t);
```

- `public static Position(Colossal.Mathematics.Line3 line, System.Single t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Line3 line, System.Single t);
```

- `public static Position(Colossal.Mathematics.Line3+Segment line, System.Single t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Line3+Segment line, System.Single t);
```

- `public static Position(Colossal.Mathematics.Tetrahedron3 tetrahedron, Unity.Mathematics.float3 t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Tetrahedron3 tetrahedron, Unity.Mathematics.float3 t);
```

- `public static Position(Colossal.Mathematics.Triangle1 triangle, Unity.Mathematics.float2 t) : System.Single`  

```csharp
public static System.Single Position(Colossal.Mathematics.Triangle1 triangle, Unity.Mathematics.float2 t);
```

- `public static Position(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 t) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Position(Colossal.Mathematics.Triangle2 triangle, Unity.Mathematics.float2 t);
```

- `public static Position(Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.float2 t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Position(Colossal.Mathematics.Triangle3 triangle, Unity.Mathematics.float2 t);
```

- `private static QuadIntersectHelper(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t) : System.Boolean`  

```csharp
private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Quad2 quad, Colossal.Mathematics.Line2+Segment line, Unity.Mathematics.float2& t);
```

- `private static QuadIntersectHelper(Unity.Mathematics.float4 x, Unity.Mathematics.float4 y, Unity.Mathematics.float2 position) : System.Boolean`  

```csharp
private static System.Boolean QuadIntersectHelper(Unity.Mathematics.float4 x, Unity.Mathematics.float4 y, Unity.Mathematics.float2 position);
```

- `private static QuadIntersectHelper(Unity.Mathematics.float4 x, Unity.Mathematics.float4 y, Unity.Mathematics.float2 p, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b) : System.Boolean`  

```csharp
private static System.Boolean QuadIntersectHelper(Unity.Mathematics.float4 x, Unity.Mathematics.float4 y, Unity.Mathematics.float2 p, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b);
```

- `public static Quantize(Unity.Mathematics.float3 v, Unity.Mathematics.float3 quant) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Quantize(Unity.Mathematics.float3 v, Unity.Mathematics.float3 quant);
```

- `private static QuantizeSnorm(System.Single v, System.Int32 N) : System.Int32`  

```csharp
private static System.Int32 QuantizeSnorm(System.Single v, System.Int32 N);
```

- `public static Right(Unity.Mathematics.float2 forward) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Right(Unity.Mathematics.float2 forward);
```

- `public static RotateLeft(Unity.Mathematics.float2 vector, System.Single angle) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 RotateLeft(Unity.Mathematics.float2 vector, System.Single angle);
```

- `public static RotateRight(Unity.Mathematics.float2 vector, System.Single angle) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 RotateRight(Unity.Mathematics.float2 vector, System.Single angle);
```

- `public static RotationAngle(Unity.Mathematics.float2 vector1, Unity.Mathematics.float2 vector2) : System.Single`  

```csharp
public static System.Single RotationAngle(Unity.Mathematics.float2 vector1, Unity.Mathematics.float2 vector2);
```

- `public static RotationAngle(Unity.Mathematics.quaternion a, Unity.Mathematics.quaternion b) : System.Single`  

```csharp
public static System.Single RotationAngle(Unity.Mathematics.quaternion a, Unity.Mathematics.quaternion b);
```

- `public static RotationAngle(System.Single fromAngle, System.Single toAngle) : System.Single`  

```csharp
public static System.Single RotationAngle(System.Single fromAngle, System.Single toAngle);
```

- `public static RotationAngleLeft(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector) : System.Single`  

```csharp
public static System.Single RotationAngleLeft(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
```

- `public static RotationAngleRight(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector) : System.Single`  

```csharp
public static System.Single RotationAngleRight(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
```

- `public static RotationAngleSignedLeft(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector) : System.Single`  

```csharp
public static System.Single RotationAngleSignedLeft(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
```

- `public static RotationAngleSignedRight(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector) : System.Single`  

```csharp
public static System.Single RotationAngleSignedRight(Unity.Mathematics.float2 fromVector, Unity.Mathematics.float2 toVector);
```

- `public static RoundToIntRandom(Unity.Mathematics.Random& random, System.Single value) : System.Int32`  

```csharp
public static System.Int32 RoundToIntRandom(Unity.Mathematics.Random& random, System.Single value);
```

- `public static RoundToIntRandom(Unity.Mathematics.Random& random, Unity.Mathematics.float4 value) : Unity.Mathematics.int4`  

```csharp
public static Unity.Mathematics.int4 RoundToIntRandom(Unity.Mathematics.Random& random, Unity.Mathematics.float4 value);
```

- `public static Size(Colossal.Mathematics.Bounds1 bounds) : System.Single`  

```csharp
public static System.Single Size(Colossal.Mathematics.Bounds1 bounds);
```

- `public static Size(Colossal.Mathematics.Bounds2 bounds) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Size(Colossal.Mathematics.Bounds2 bounds);
```

- `public static Size(Colossal.Mathematics.Bounds3 bounds) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Size(Colossal.Mathematics.Bounds3 bounds);
```

- `public static SmoothDamp(System.Single current, System.Single target, System.Single& currentVelocity, System.Single smoothTime, System.Single maxSpeed, System.Single deltaTime) : System.Single`  

```csharp
public static System.Single SmoothDamp(System.Single current, System.Single target, System.Single& currentVelocity, System.Single smoothTime, System.Single maxSpeed, System.Single deltaTime);
```

- `public static Snap(System.Single value, System.Single interval) : System.Single`  

```csharp
public static System.Single Snap(System.Single value, System.Single interval);
```

- `public static Snap(Unity.Mathematics.float2 value, Unity.Mathematics.float2 interval) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Snap(Unity.Mathematics.float2 value, Unity.Mathematics.float2 interval);
```

- `public static Snap(System.Single value, System.Single interval, System.Single offset) : System.Single`  

```csharp
public static System.Single Snap(System.Single value, System.Single interval, System.Single offset);
```

- `public static Snap(Unity.Mathematics.float2 value, Unity.Mathematics.float2 interval, Unity.Mathematics.float2 offset) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Snap(Unity.Mathematics.float2 value, Unity.Mathematics.float2 interval, Unity.Mathematics.float2 offset);
```

- `public static Sphere(Colossal.Mathematics.Sphere3 sphere1, Colossal.Mathematics.Sphere3 sphere2) : Colossal.Mathematics.Sphere3`  

```csharp
public static Colossal.Mathematics.Sphere3 Sphere(Colossal.Mathematics.Sphere3 sphere1, Colossal.Mathematics.Sphere3 sphere2);
```

- `public static StartReflect(Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bezier4x3`  

```csharp
public static Colossal.Mathematics.Bezier4x3 StartReflect(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static StartTangent(Colossal.Mathematics.Bezier4x1 curve) : System.Single`  

```csharp
public static System.Single StartTangent(Colossal.Mathematics.Bezier4x1 curve);
```

- `public static StartTangent(Colossal.Mathematics.Bezier4x2 curve) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 StartTangent(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static StartTangent(Colossal.Mathematics.Bezier4x3 curve) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 StartTangent(Colossal.Mathematics.Bezier4x3 curve);
```

- `public static Tangent(Colossal.Mathematics.Bezier4x1 curve, System.Single t) : System.Single`  

```csharp
public static System.Single Tangent(Colossal.Mathematics.Bezier4x1 curve, System.Single t);
```

- `public static Tangent(Colossal.Mathematics.Bezier4x2 curve, System.Single t) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Tangent(Colossal.Mathematics.Bezier4x2 curve, System.Single t);
```

- `public static Tangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Tangent(Colossal.Mathematics.Bezier4x3 curve, System.Single t);
```

- `public static Tangent(Colossal.Mathematics.Line1 line) : System.Single`  

```csharp
public static System.Single Tangent(Colossal.Mathematics.Line1 line);
```

- `public static Tangent(Colossal.Mathematics.Line1+Segment line) : System.Single`  

```csharp
public static System.Single Tangent(Colossal.Mathematics.Line1+Segment line);
```

- `public static Tangent(Colossal.Mathematics.Line2 line) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Tangent(Colossal.Mathematics.Line2 line);
```

- `public static Tangent(Colossal.Mathematics.Line2+Segment line) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 Tangent(Colossal.Mathematics.Line2+Segment line);
```

- `public static Tangent(Colossal.Mathematics.Line3 line) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Tangent(Colossal.Mathematics.Line3 line);
```

- `public static Tangent(Colossal.Mathematics.Line3+Segment line) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 Tangent(Colossal.Mathematics.Line3+Segment line);
```

- `public static TangentToOctahedral(Unity.Mathematics.float4 t) : System.UInt32`  

```csharp
public static System.UInt32 TangentToOctahedral(Unity.Mathematics.float4 t);
```

- `public static TightBounds(Colossal.Mathematics.Bezier4x2 curve) : Colossal.Mathematics.Bounds2`  

```csharp
public static Colossal.Mathematics.Bounds2 TightBounds(Colossal.Mathematics.Bezier4x2 curve);
```

- `public static TightBounds(Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 TightBounds(Colossal.Mathematics.Bezier4x3 curve);
```

- `private static TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Box3 box1, Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 pos1, Unity.Mathematics.float3 pos2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 pos1, Unity.Mathematics.float3 pos2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Tetrahedron3 tetrahedron1, Unity.Mathematics.float3 pos1, Unity.Mathematics.float3 pos2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Tetrahedron3 tetrahedron1, Unity.Mathematics.float3 pos1, Unity.Mathematics.float3 pos2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.TrigonalTrapezohedron3 trapezohedron1, Colossal.Mathematics.Bounds3 bounds1, Unity.Mathematics.float3 a1, Unity.Mathematics.float3 b1, Unity.Mathematics.float3 a2, Unity.Mathematics.float3 b2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TrapezohedronBoxIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TriangleIntersectAddFirstEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, System.Single startT, System.Single endT, Colossal.Mathematics.Bounds2 bounds) : System.Void`  

```csharp
private static System.Void TriangleIntersectAddFirstEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, System.Single startT, System.Single endT, Colossal.Mathematics.Bounds2 bounds);
```

- `private static TriangleIntersectAddNextEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, System.Single startT, System.Single endT, Colossal.Mathematics.Bounds2 bounds, System.Single& area) : System.Void`  

```csharp
private static System.Void TriangleIntersectAddNextEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Unity.Mathematics.float2 a, Unity.Mathematics.float2 b, System.Single startT, System.Single endT, Colossal.Mathematics.Bounds2 bounds, System.Single& area);
```

- `private static TriangleIntersectCheckLastEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Colossal.Mathematics.Bounds2 bounds, System.Single& area) : System.Void`  

```csharp
private static System.Void TriangleIntersectCheckLastEdge(Colossal.Mathematics.Triangle2& buffer, Unity.Mathematics.int2& sides, Colossal.Mathematics.Bounds2 bounds, System.Single& area);
```

- `private static TriangleIntersectHelper(Unity.Mathematics.float3 x, Unity.Mathematics.float3 y, Unity.Mathematics.float2 position) : System.Boolean`  

```csharp
private static System.Boolean TriangleIntersectHelper(Unity.Mathematics.float3 x, Unity.Mathematics.float3 y, Unity.Mathematics.float2 position);
```

- `public static TryNormalize(Unity.Mathematics.float2& value) : System.Boolean`  

```csharp
public static System.Boolean TryNormalize(Unity.Mathematics.float2& value);
```

- `public static TryNormalize(Unity.Mathematics.float3& value) : System.Boolean`  

```csharp
public static System.Boolean TryNormalize(Unity.Mathematics.float3& value);
```

- `public static TryNormalize(Unity.Mathematics.float2& value, System.Single newLength) : System.Boolean`  

```csharp
public static System.Boolean TryNormalize(Unity.Mathematics.float2& value, System.Single newLength);
```

- `public static TryNormalize(Unity.Mathematics.float3& value, System.Single newLength) : System.Boolean`  

```csharp
public static System.Boolean TryNormalize(Unity.Mathematics.float3& value, System.Single newLength);
```


