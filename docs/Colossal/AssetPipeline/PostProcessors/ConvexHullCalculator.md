# Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face> faces`  
- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+PointFace> openSet`  
- `private System.Collections.Generic.HashSet<System.Int32> litFaces`  
- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+HorizonEdge> horizon`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Int32> hullVerts`  
- `private System.Int32 openSetTail`  
- `private System.Int32 faceCount`  
- `private static const System.Int32 UNASSIGNED`  
- `private static const System.Int32 INSIDE`  
- `private static const System.Single EPSILON`  

## Constructors

- `public ConvexHullCalculator()`  

## Methods

- `private AreCoincident(UnityEngine.Vector3 a, UnityEngine.Vector3 b) : System.Boolean`  
- `private AreCollinear(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c) : System.Boolean`  
- `private AreCoplanar(UnityEngine.Vector3 a, UnityEngine.Vector3 b, UnityEngine.Vector3 c, UnityEngine.Vector3 d) : System.Boolean`  
- `private static Assert(System.Boolean condition) : System.Void`  
- `private ConstructCone(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32 farthestPoint) : System.Void`  
- `private static Cross(UnityEngine.Vector3 a, UnityEngine.Vector3 b) : UnityEngine.Vector3`  
- `private static Dot(UnityEngine.Vector3 a, UnityEngine.Vector3 b) : System.Single`  
- `private ExportMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals) : System.Void`  
- `private FindHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 fi, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face) : System.Void`  
- `private FindInitialHullIndices(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Int32& b0, System.Int32& b1, System.Int32& b2, System.Int32& b3) : System.Void`  
- `public GenerateHull(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& normals) : System.Void`  
- `private GenerateInitialHull(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  
- `private GrowHull(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  
- `private HasEdge(Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face f, System.Int32 e0, System.Int32 e1) : System.Boolean`  
- `private Initialize(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Boolean splitVerts) : System.Void`  
- `private Normal(UnityEngine.Vector3 v0, UnityEngine.Vector3 v1, UnityEngine.Vector3 v2) : UnityEngine.Vector3`  
- `private PointFaceDistance(UnityEngine.Vector3 point, UnityEngine.Vector3 pointOnFace, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face) : System.Single`  
- `private ReassignPoints(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  
- `private SearchHorizon(System.Collections.Generic.List<UnityEngine.Vector3> points, UnityEngine.Vector3 point, System.Int32 prevFaceIndex, System.Int32 faceCount, Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face face) : System.Void`  
- `private VerifyFaces(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  
- `private VerifyHorizon() : System.Void`  
- `private VerifyMesh(System.Collections.Generic.List<UnityEngine.Vector3> points, System.Collections.Generic.List`1[[UnityEngine.Vector3, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& verts, System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& tris) : System.Void`  
- `private VerifyOpenSet(System.Collections.Generic.List<UnityEngine.Vector3> points) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+Face`  
- `Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+PointFace`  
- `Colossal.AssetPipeline.PostProcessors.ConvexHullCalculator+HorizonEdge`  

