# Colossal.Internal.Gizmos.RenderData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Colossal.NativeCounter+Concurrent m_ConcurrentVertexCount`  
- `public Colossal.NativeCounter+Concurrent m_ConcurrentIndicesCount`  
- `private System.Void* m_Vertices`  
- `private System.Void* m_Colors`  
- `private System.Void* m_Indices`  

## Properties

- `public System.Int32 concurrentVertexCount { get }`  

## Constructors

- `public RenderData(UnityEngine.Vector3[] vertices, UnityEngine.Color[] colors, System.Int32[] indices, Colossal.NativeCounter& vertexCount, Colossal.NativeCounter& indicesCount)`  

## Methods

- `public AddLineIndices(System.Int32 a, System.Int32 b) : System.Void`  
- `public AddVertex(Unity.Mathematics.float3 v, UnityEngine.Color c) : System.Int32`  
- `public Dispose() : System.Void`  

