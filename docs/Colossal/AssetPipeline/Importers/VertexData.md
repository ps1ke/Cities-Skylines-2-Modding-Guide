# Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>`  

## Fields

- `private UnityEngine.Rendering.VertexAttribute <attribute>k__BackingField`  
- `private UnityEngine.Rendering.VertexAttributeFormat <format>k__BackingField`  
- `private System.Int32 <dimension>k__BackingField`  
- `private Unity.Collections.NativeArray<System.Byte> <data>k__BackingField`  
- `private System.Boolean <isPacked>k__BackingField`  

## Properties

- `public UnityEngine.Rendering.VertexAttribute attribute { get; private set }`  
- `public UnityEngine.Rendering.VertexAttributeFormat format { get; private set }`  
- `public System.Int32 dimension { get; private set }`  
- `public Unity.Collections.NativeArray<System.Byte> data { get; private set }`  
- `public System.Boolean isPacked { get; private set }`  
- `public System.Int32 elementSize { get }`  

## Constructors

- `public VertexData(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArray<System.Byte> data, System.Boolean isPacked = False)`  

## Methods

- `public ChangeAttribute(UnityEngine.Rendering.VertexAttribute attribute) : System.Void`  
- `public CompareTo(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData other) : System.Int32`  
- `public Convert(UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Boolean`  
- `public Dispose() : System.Void`  
- `public SetNewData<T>(Unity.Collections.NativeArray<T> newData) : System.Void`  

