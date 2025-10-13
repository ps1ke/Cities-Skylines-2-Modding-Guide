# Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ConvexHullCalculator
{
    private System.Collections.Generic.Dictionary<System.Int32, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face> faces;
    private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+PointFace> openSet;
    private System.Collections.Generic.HashSet<System.Int32> litFaces;
    private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+HorizonEdge> horizon;
    private System.Collections.Generic.Dictionary<System.Int32, System.Int32> hullVerts;
    private System.Int32 openSetTail;
    private System.Int32 faceCount;
    private static const System.Int32 UNASSIGNED;
    private static const System.Int32 INSIDE;
    private static const System.Single EPSILON;

    public ConvexHullCalculator();

    private System.Boolean AreCoincident(UnityEngine.Vector3 a, UnityEngine.Vector3 b);
    private System.Boolean AreCollinear(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c);
    private System.Boolean AreCoplanar(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c, UnityEngine.Vector3 d);
    private static System.Void Assert(System.Boolean condition);
    private System.Void ConstructCone(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32 farthestPoint);
    private static UnityEngine.Vector3 Cross(UnityEngine.Vector3 a, UnityEngine.Vector3 b);
    private static System.Single Dot(UnityEngine.Vector3 a, UnityEngine.Vector3 b);
    private System.Void ExportMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals);
    private System.Void FindHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 fi, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face);
    private System.Void FindInitialHullIndices(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32& b0, System.Int32& b1, System.Int32& b2, System.Int32& b3);
    public System.Void GenerateHull(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals);
    private System.Void GenerateInitialHull(System.Collections.Generic.List<UnityEngine.Vector3> points);
    private System.Void GrowHull(System.Collections.Generic.List<UnityEngine.Vector3> points);
    private System.Boolean HasEdge(Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face f, System.Int32 e0, System.Int32 e1);
    private System.Void Initialize(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts);
    private UnityEngine.Vector3 Normal(UnityEngine.Vector3 v0, UnityEngine.Vector3 v1, UnityEngine.Vector3 v2);
    private System.Single PointFaceDistance(UnityEngine.Vector3 point, UnityEngine.Vector3 pointOnFace, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face);
    private System.Void ReassignPoints(System.Collections.Generic.List<UnityEngine.Vector3> points);
    private System.Void SearchHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 prevFaceIndex, System.Int32 faceCount, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face);
    private System.Void VerifyFaces(System.Collections.Generic.List<UnityEngine.Vector3> points);
    private System.Void VerifyHorizon();
    private System.Void VerifyMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris);
    private System.Void VerifyOpenSet(System.Collections.Generic.List<UnityEngine.Vector3> points);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face> faces`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face> faces;
```

- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+PointFace> openSet`  

```csharp
private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+PointFace> openSet;
```

- `private System.Collections.Generic.HashSet<System.Int32> litFaces`  

```csharp
private System.Collections.Generic.HashSet<System.Int32> litFaces;
```

- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+HorizonEdge> horizon`  

```csharp
private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+HorizonEdge> horizon;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Int32> hullVerts`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Int32> hullVerts;
```

- `private System.Int32 openSetTail`  

```csharp
private System.Int32 openSetTail;
```

- `private System.Int32 faceCount`  

```csharp
private System.Int32 faceCount;
```

- `private static const System.Int32 UNASSIGNED`  

```csharp
private static const System.Int32 UNASSIGNED;
```

- `private static const System.Int32 INSIDE`  

```csharp
private static const System.Int32 INSIDE;
```

- `private static const System.Single EPSILON`  

```csharp
private static const System.Single EPSILON;
```


## Constructors

- `public ConvexHullCalculator()`  

```csharp
public ConvexHullCalculator();
```


## Methods

- `private AreCoincident(UnityEngine.Vector3 a, UnityEngine.Vector3 b) : System.Boolean`  

```csharp
private System.Boolean AreCoincident(UnityEngine.Vector3 a, UnityEngine.Vector3 b);
```

- `private AreCollinear(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c) : System.Boolean`  

```csharp
private System.Boolean AreCollinear(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c);
```

- `private AreCoplanar(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c, UnityEngine.Vector3 d) : System.Boolean`  

```csharp
private System.Boolean AreCoplanar(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c, UnityEngine.Vector3 d);
```

- `private static Assert(System.Boolean condition) : System.Void`  

```csharp
private static System.Void Assert(System.Boolean condition);
```

- `private ConstructCone(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32 farthestPoint) : System.Void`  

```csharp
private System.Void ConstructCone(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32 farthestPoint);
```

- `private static Cross(UnityEngine.Vector3 a, UnityEngine.Vector3 b) : UnityEngine.Vector3`  

```csharp
private static UnityEngine.Vector3 Cross(UnityEngine.Vector3 a, UnityEngine.Vector3 b);
```

- `private static Dot(UnityEngine.Vector3 a, UnityEngine.Vector3 b) : System.Single`  

```csharp
private static System.Single Dot(UnityEngine.Vector3 a, UnityEngine.Vector3 b);
```

- `private ExportMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals) : System.Void`  

```csharp
private System.Void ExportMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals);
```

- `private FindHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 fi, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face) : System.Void`  

```csharp
private System.Void FindHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 fi, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face);
```

- `private FindInitialHullIndices(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32& b0, System.Int32& b1, System.Int32& b2, System.Int32& b3) : System.Void`  

```csharp
private System.Void FindInitialHullIndices(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32& b0, System.Int32& b1, System.Int32& b2, System.Int32& b3);
```

- `public GenerateHull(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals) : System.Void`  

```csharp
public System.Void GenerateHull(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals);
```

- `private GenerateInitialHull(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  

```csharp
private System.Void GenerateInitialHull(System.Collections.Generic.List<UnityEngine.Vector3> points);
```

- `private GrowHull(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  

```csharp
private System.Void GrowHull(System.Collections.Generic.List<UnityEngine.Vector3> points);
```

- `private HasEdge(Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face f, System.Int32 e0, System.Int32 e1) : System.Boolean`  

```csharp
private System.Boolean HasEdge(Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face f, System.Int32 e0, System.Int32 e1);
```

- `private Initialize(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts) : System.Void`  

```csharp
private System.Void Initialize(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts);
```

- `private Normal(UnityEngine.Vector3 v0, UnityEngine.Vector3 v1, UnityEngine.Vector3 v2) : UnityEngine.Vector3`  

```csharp
private UnityEngine.Vector3 Normal(UnityEngine.Vector3 v0, UnityEngine.Vector3 v1, UnityEngine.Vector3 v2);
```

- `private PointFaceDistance(UnityEngine.Vector3 point, UnityEngine.Vector3 pointOnFace, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face) : System.Single`  

```csharp
private System.Single PointFaceDistance(UnityEngine.Vector3 point, UnityEngine.Vector3 pointOnFace, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face);
```

- `private ReassignPoints(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  

```csharp
private System.Void ReassignPoints(System.Collections.Generic.List<UnityEngine.Vector3> points);
```

- `private SearchHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 prevFaceIndex, System.Int32 faceCount, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face) : System.Void`  

```csharp
private System.Void SearchHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 prevFaceIndex, System.Int32 faceCount, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face);
```

- `private VerifyFaces(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  

```csharp
private System.Void VerifyFaces(System.Collections.Generic.List<UnityEngine.Vector3> points);
```

- `private VerifyHorizon() : System.Void`  

```csharp
private System.Void VerifyHorizon();
```

- `private VerifyMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris) : System.Void`  

```csharp
private System.Void VerifyMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris);
```

- `private VerifyOpenSet(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  

```csharp
private System.Void VerifyOpenSet(System.Collections.Generic.List<UnityEngine.Vector3> points);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face`  
- `Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+PointFace`  
- `Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+HorizonEdge`  

