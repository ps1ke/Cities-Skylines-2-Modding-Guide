# Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.InteriorMapping`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island> m_Islands`  
- `private UnityEngine.Bounds m_Bounds`  
- `private System.Boolean m_Empty`  
- `private Unity.Mathematics.float3 <normal>k__BackingField`  
- `private Unity.Mathematics.float3 <tangent>k__BackingField`  
- `private Unity.Mathematics.float3 <up>k__BackingField`  
- `private Unity.Mathematics.float3 <center>k__BackingField`  
- `private System.Single <width>k__BackingField`  
- `private System.Single <height>k__BackingField`  
- `private System.Int32 <room>k__BackingField`  
- `private System.Int32 <roomIndex>k__BackingField`  
- `private System.Int32 <floor>k__BackingField`  

## Properties

- `public Unity.Mathematics.float3 normal { get; private set }`  
- `public Unity.Mathematics.float3 tangent { get; private set }`  
- `public Unity.Mathematics.float3 up { get; private set }`  
- `public Unity.Mathematics.float3 center { get; private set }`  
- `public System.Single width { get; private set }`  
- `public System.Single height { get; private set }`  
- `public System.Int32 room { get; private set }`  
- `public System.Int32 roomIndex { get; set }`  
- `public System.Int32 floor { get; set }`  
- `public UnityEngine.Bounds bounds { get }`  
- `public System.Boolean valid { get }`  
- `public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> triangles { get }`  

## Constructors

- `public Window()`  

## Methods

- `public AddIsland(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Island island) : System.Boolean`  
- `public CalculateNormalTangent(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals, System.ReadOnlySpan<Unity.Mathematics.float3> vertices) : System.Void`  
- `private static DetectFacing(Unity.Mathematics.float3 normal) : System.Int32`  
- `public DetermineRoom(System.ReadOnlySpan<Unity.Mathematics.float2> uvs, System.ReadOnlySpan<System.Int32> indices) : System.Void`  
- `public Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window) : System.Boolean`  
- `public Split(System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> normals) : System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window>`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window+<get_triangles>d__44`  

