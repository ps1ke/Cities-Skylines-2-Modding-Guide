# Colossal.AssetPipeline.PostProcessors.Emissive.Helpers

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Emissive`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `private static DrawErrorTriangleWithColor(Colossal.AssetPipeline.PostProcessors.Emissive.ErrorTexture errorOutput, Unity.Mathematics.float2 p0, Unity.Mathematics.float2 p1, Unity.Mathematics.float2 p2, UnityEngine.Color32 color) : System.Void`  
- `private static FindCornerTriangle(System.Collections.Generic.List<System.Int32> triangles, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.Int32>> vertexMap, Unity.Mathematics.float2& corner) : System.Int32`  
- `public static GatherTriangleGroups(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.Int32>> vertexToTriangle, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& groups) : System.Void`  
- `public static GatherTriangles(Colossal.AssetPipeline.PostProcessors.Emissive.EmissiveSourceTextures source, Unity.Collections.NativeArray<System.Int32> indices, Unity.Collections.NativeArray<Unity.Mathematics.float2> uv, System.Int32 width, System.Int32 height, System.Collections.Generic.List`1[[Colossal.AssetPipeline.PostProcessors.Emissive.Triangle, Colossal.AssetPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangleList, System.Collections.Generic.Dictionary`2[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e],[System.Collections.Generic.List`1[[System.Int32, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& vertexToTriangleMap, Colossal.AssetPipeline.PostProcessors.Emissive.ErrorTexture errorOutput) : System.Boolean`  
- `private static GatherTrianglesGroup(System.Boolean[] processed, System.Int32 triIndex, Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup group, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.Int32>> vertexToTriangle) : System.Void`  
- `private static GetNextTriangle(Unity.Mathematics.float2 center, System.Collections.Generic.List<System.Int32> explore, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList) : System.Int32`  
- `private static GetXY(Unity.Collections.NativeArray<Unity.Mathematics.float2> uv, System.Int32 index, System.Int32 width, System.Int32 height) : UnityEngine.Vector2Int`  
- `public static PreserveOrdering(System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> splitGroups, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> groups) : System.Void`  
- `public static SortGroup(Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup group, System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<System.Int32>> vertexMap, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList) : System.Void`  
- `public static SplitGroups(Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup group, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.Triangle> triangleList, Colossal.AssetPipeline.PostProcessors.Emissive.MeshData meshData, System.Span<System.Int32> indices, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.Emissive.TriangleGroup> outGroup) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.Emissive.Helpers+ErrorTriangleShader`  
- `Colossal.AssetPipeline.PostProcessors.Emissive.Helpers+GatherTriLightsShader`  

