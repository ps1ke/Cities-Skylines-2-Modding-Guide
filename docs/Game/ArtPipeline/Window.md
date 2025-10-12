# Game.ArtPipeline.InteriorMappingProcessor+Window

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Island> m_Islands`  
- `private UnityEngine.Bounds m_Bounds`  
- `private System.Boolean m_Empty`  
- `private UnityEngine.Vector3 <normal>k__BackingField`  
- `private UnityEngine.Vector3 <tangent>k__BackingField`  
- `private UnityEngine.Vector3 <up>k__BackingField`  
- `private UnityEngine.Vector3 <center>k__BackingField`  
- `private System.Single <width>k__BackingField`  
- `private System.Single <height>k__BackingField`  
- `private System.Int32 <room>k__BackingField`  
- `private System.Int32 <roomIndex>k__BackingField`  
- `private System.Int32 <floor>k__BackingField`  

## Properties

- `public UnityEngine.Vector3 normal { get; private set }`  
- `public UnityEngine.Vector3 tangent { get; private set }`  
- `public UnityEngine.Vector3 up { get; private set }`  
- `public UnityEngine.Vector3 center { get; private set }`  
- `public System.Single width { get; private set }`  
- `public System.Single height { get; private set }`  
- `public System.Int32 room { get; private set }`  
- `public System.Int32 roomIndex { get; set }`  
- `public System.Int32 floor { get; set }`  
- `public UnityEngine.Bounds bounds { get }`  
- `public System.Boolean valid { get }`  
- `public System.Collections.Generic.IEnumerable<Game.ArtPipeline.InteriorMappingProcessor+Triangle> triangles { get }`  

## Constructors

- `public Window()`  

## Methods

- `public AddIsland(Game.ArtPipeline.InteriorMappingProcessor+Island island) : System.Boolean`  
- `public CalculateNormalTangent(System.Int32[] indices, UnityEngine.Vector3[] normals, UnityEngine.Vector3[] vertices) : System.Void`  
- `private static DeterimineFace(UnityEngine.Vector3 normal) : System.Int32`  
- `public DetermineRoom(System.Collections.Generic.List<UnityEngine.Vector4> uvs, System.Int32[] Indices) : System.Void`  
- `public Merge(Game.ArtPipeline.InteriorMappingProcessor+Window window) : System.Boolean`  
- `public Split(System.Int32[] indices, UnityEngine.Vector3[] normals) : System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window>`  

## Nested types

- `Game.ArtPipeline.InteriorMappingProcessor+Window+<get_triangles>d__44`  

