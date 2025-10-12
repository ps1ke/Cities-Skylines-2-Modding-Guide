# Game.ArtPipeline.InteriorMappingProcessor

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Constructors

- `public InteriorMappingProcessor()`  

## Methods

- `public static BakeInteriorWindows(UnityEngine.Mesh source, System.Int32 submesh, Game.ArtPipeline.InteriorMappingProcessor+BakeMode mode, System.Single floorHeight = 3, System.Single maxWindowDistance = 2) : System.Void`  
- `public static BakeInteriorWindows(UnityEngine.Mesh source, System.Int32 submesh, Game.ArtPipeline.InteriorMappingProcessor+BakeMode mode, Game.ArtPipeline.InteriorMappingProcessor+DebugData& debugData, System.Single floorHeight = 3, System.Single maxWindowDistance = 2) : System.Void`  
- `private static BakeInteriorWindows_Tangent(UnityEngine.Mesh source, System.Int32 submesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> windows, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Room> rooms, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Void`  
- `private static BakeInteriorWindows_WindowSpace(UnityEngine.Mesh source, System.Int32 submesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> windows, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Room> rooms, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Void`  
- `private static BakeInteriorWindows_WindowSpaceOverride(UnityEngine.Mesh source, System.Int32 submesh, System.Single floorHeight, System.Single maxWindowDistance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> windows, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Room> rooms, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Void`  
- `private static BuildRooms(System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Room> result, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> windows, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors, System.Single MaxWindowDistance) : System.Void`  
- `private static BuildWindows(System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> windows, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Island> islands, System.Int32[] indices, UnityEngine.Vector3[] normals, UnityEngine.Vector3[] vertices, System.Collections.Generic.List<UnityEngine.Vector4> originalUV, System.Single floorHeight) : System.Void`  
- `private static ClosestDistance(UnityEngine.Bounds a, UnityEngine.Bounds b) : System.Single`  
- `private static Encode(System.Int32 Facing, System.Int32 roomId, System.Int32 Index) : System.Int32`  
- `private static ExtractFloors(System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window> windows, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> outFloors, System.Single floorHeight) : System.Void`  
- `private static ExtractTriangles(System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles, UnityEngine.Vector3[] vertices, System.Int32[] indices) : System.Void`  
- `private static FromInt(System.Int32 Value) : UnityEngine.Color32`  
- `private static GenerateTrianglesAndIslands(UnityEngine.Vector3[] vertices, System.Int32[] indices, System.Collections.Generic.List`1[[Game.ArtPipeline.InteriorMappingProcessor+Triangle, Game.ArtPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& triangles, System.Collections.Generic.List`1[[Game.ArtPipeline.InteriorMappingProcessor+Island, Game.ArtPipeline, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& islands) : System.Void`  
- `private static UpdateUVs(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Int32 Data, System.Int32[] indices, UnityEngine.Color32[] colors, UnityEngine.Vector3[] vertices, System.Collections.Generic.List<UnityEngine.Vector4> uvs, System.Collections.Generic.List<UnityEngine.Vector4> windowRotation, UnityEngine.Vector3 tangent, UnityEngine.Vector3 up, UnityEngine.Vector3 normal, UnityEngine.Vector3 center, System.Single width, System.Single height) : System.Void`  
- `private static UpdateUVs(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Int32 Data, System.Int32[] indices, UnityEngine.Color32[] colors, UnityEngine.Vector3[] vertices, System.Collections.Generic.List<UnityEngine.Vector4> uvs, System.Collections.Generic.List<UnityEngine.Vector3> windowNormals, System.Collections.Generic.List<UnityEngine.Vector4> windowTangents, UnityEngine.Vector3 tangent, UnityEngine.Vector3 up, UnityEngine.Vector3 normal, UnityEngine.Vector3 center, System.Single width, System.Single height) : System.Void`  

## Nested types

- `Game.ArtPipeline.InteriorMappingProcessor+DebugData`  
- `Game.ArtPipeline.InteriorMappingProcessor+BakeMode`  
- `Game.ArtPipeline.InteriorMappingProcessor+Triangle`  
- `Game.ArtPipeline.InteriorMappingProcessor+Island`  
- `Game.ArtPipeline.InteriorMappingProcessor+Floor`  
- `Game.ArtPipeline.InteriorMappingProcessor+RoomFacing`  
- `Game.ArtPipeline.InteriorMappingProcessor+Room`  
- `Game.ArtPipeline.InteriorMappingProcessor+Window`  
- `Game.ArtPipeline.InteriorMappingProcessor+Slice`  
- `Game.ArtPipeline.InteriorMappingProcessor+ScoredSlice`  
- `Game.ArtPipeline.InteriorMappingProcessor+<>c`  

