# Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.InteriorMapping`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.HashSet<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> m_Neighbours`  
- `private UnityEngine.Bounds <bounds>k__BackingField`  
- `private System.Int32 <startIndex>k__BackingField`  
- `private System.Boolean <added>k__BackingField`  

## Properties

- `public UnityEngine.Bounds bounds { get; private set }`  
- `public System.Int32 startIndex { get; private set }`  
- `public System.Boolean added { get; set }`  
- `public System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle> neighbours { get }`  

## Constructors

- `public Triangle(System.Int32 startIndex, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<Unity.Mathematics.float3> vertices)`  

## Methods

- `public AddNeighbour(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle tri) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.Triangle+<get_neighbours>d__16`  

