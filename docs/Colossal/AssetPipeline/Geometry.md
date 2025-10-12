# Colossal.AssetPipeline.Geometry

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Fields

- `public System.Action<UnityEngine.GameObject> OnPostDebugOutput`  
- `public Colossal.AssetPipeline.Importers.ModelImporter+Model[] models`  

## Properties

- `public System.String name { get }`  
- `public System.Boolean hasSkin { get }`  
- `public System.Boolean isValid { get }`  

## Constructors

- `public Geometry(Colossal.AssetPipeline.Importers.ModelImporter+Model[] models)`  

## Methods

- `public CalcBounds() : Colossal.Mathematics.Bounds3`  
- `public CalcSurfaceArea() : System.Single`  
- `public CalcTotalIndices() : System.Int32`  
- `public CalcTotalVertices() : System.Int32`  
- `public Dispose() : System.Void`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public ToUnityMeshes(System.Boolean hideAndDontSave = True) : UnityEngine.Mesh[]`  

