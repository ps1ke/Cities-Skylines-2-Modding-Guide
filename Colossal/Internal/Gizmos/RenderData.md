# Colossal.Internal.Gizmos.RenderData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RenderData
{
    public Colossal.NativeCounter+Concurrent m_ConcurrentVertexCount;
    public Colossal.NativeCounter+Concurrent m_ConcurrentIndicesCount;
    private System.Void* m_Vertices;
    private System.Void* m_Colors;
    private System.Void* m_Indices;

    public System.Int32 concurrentVertexCount { get; }

    public RenderData(UnityEngine.Vector3[] vertices, UnityEngine.Color[] colors, System.Int32[] indices, Colossal.NativeCounter& vertexCount, Colossal.NativeCounter& indicesCount);

    public System.Void AddLineIndices(System.Int32 a, System.Int32 b);
    public System.Int32 AddVertex(Unity.Mathematics.float3 v, UnityEngine.Color c);
    public System.Void Dispose();
}
```


## Fields

- `public Colossal.NativeCounter+Concurrent m_ConcurrentVertexCount`  

```csharp
public Colossal.NativeCounter+Concurrent m_ConcurrentVertexCount;
```

- `public Colossal.NativeCounter+Concurrent m_ConcurrentIndicesCount`  

```csharp
public Colossal.NativeCounter+Concurrent m_ConcurrentIndicesCount;
```

- `private System.Void* m_Vertices`  

```csharp
private System.Void* m_Vertices;
```

- `private System.Void* m_Colors`  

```csharp
private System.Void* m_Colors;
```

- `private System.Void* m_Indices`  

```csharp
private System.Void* m_Indices;
```


## Properties

- `public System.Int32 concurrentVertexCount { get }`  

```csharp
public System.Int32 concurrentVertexCount { get; }
```


## Constructors

- `public RenderData(UnityEngine.Vector3[] vertices, UnityEngine.Color[] colors, System.Int32[] indices, Colossal.NativeCounter& vertexCount, Colossal.NativeCounter& indicesCount)`  

```csharp
public RenderData(UnityEngine.Vector3[] vertices, UnityEngine.Color[] colors, System.Int32[] indices, Colossal.NativeCounter& vertexCount, Colossal.NativeCounter& indicesCount);
```


## Methods

- `public AddLineIndices(System.Int32 a, System.Int32 b) : System.Void`  

```csharp
public System.Void AddLineIndices(System.Int32 a, System.Int32 b);
```

- `public AddVertex(Unity.Mathematics.float3 v, UnityEngine.Color c) : System.Int32`  

```csharp
public System.Int32 AddVertex(Unity.Mathematics.float3 v, UnityEngine.Color c);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


