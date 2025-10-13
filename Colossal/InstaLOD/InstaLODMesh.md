# Colossal.InstaLOD.InstaLODMesh

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct InstaLODMesh
{
    internal System.IntPtr m_Ptr;
    private Colossal.InstaLOD.InstaLODSDK m_SDK;

    public System.Boolean isValid { get; }
    public System.Int32 calcSubMeshCount { get; }

    public InstaLODMesh(Colossal.InstaLOD.InstaLODSDK sdk);

    public System.Void Append(Colossal.InstaLOD.InstaLODMesh meshToAppend);
    public System.Void CheckAndSanitize();
    public System.Void Clear();
    public System.Void Dispose();
    public Colossal.InstaLOD.InstaLODMesh ExtractSubMesh(System.Int32 id);
    public Colossal.InstaLOD.MeshData GetData();
    public System.Void SetAttribute<T>(UnityEngine.Rendering.VertexAttribute attr, System.ReadOnlySpan<T> data);
    public System.Void SetAttribute(UnityEngine.Rendering.VertexAttribute attr, System.Int32 count, System.Int32 strideBytes, System.IntPtr ptr);
    public System.Void SetIndices(System.ReadOnlySpan<System.Int32> data);
    public System.Void SetSkinning(System.Int32 bonesPerVertex, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<System.Single> weights);
    public System.Void SetSkinning(System.Int32 vertexCount, System.Int32 bonesPerVertex, System.Void* indices, System.Void* weights);
    public System.Void SetTriangleMaterialIDs(System.ReadOnlySpan<System.Int32> data);
    public System.Void SetTriangleSubMeshIDs(System.ReadOnlySpan<System.Int32> data);
}
```


## Fields

- `internal System.IntPtr m_Ptr`  

```csharp
internal System.IntPtr m_Ptr;
```

- `private Colossal.InstaLOD.InstaLODSDK m_SDK`  

```csharp
private Colossal.InstaLOD.InstaLODSDK m_SDK;
```


## Properties

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Int32 calcSubMeshCount { get }`  

```csharp
public System.Int32 calcSubMeshCount { get; }
```


## Constructors

- `public InstaLODMesh(Colossal.InstaLOD.InstaLODSDK sdk)`  

```csharp
public InstaLODMesh(Colossal.InstaLOD.InstaLODSDK sdk);
```


## Methods

- `public Append(Colossal.InstaLOD.InstaLODMesh meshToAppend) : System.Void`  

```csharp
public System.Void Append(Colossal.InstaLOD.InstaLODMesh meshToAppend);
```

- `public CheckAndSanitize() : System.Void`  

```csharp
public System.Void CheckAndSanitize();
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ExtractSubMesh(System.Int32 id) : Colossal.InstaLOD.InstaLODMesh`  

```csharp
public Colossal.InstaLOD.InstaLODMesh ExtractSubMesh(System.Int32 id);
```

- `public GetData() : Colossal.InstaLOD.MeshData`  

```csharp
public Colossal.InstaLOD.MeshData GetData();
```

- `public SetAttribute<T>(UnityEngine.Rendering.VertexAttribute attr, System.ReadOnlySpan<T> data) : System.Void`  

```csharp
public System.Void SetAttribute<T>(UnityEngine.Rendering.VertexAttribute attr, System.ReadOnlySpan<T> data);
```

- `public SetAttribute(UnityEngine.Rendering.VertexAttribute attr, System.Int32 count, System.Int32 strideBytes, System.IntPtr ptr) : System.Void`  

```csharp
public System.Void SetAttribute(UnityEngine.Rendering.VertexAttribute attr, System.Int32 count, System.Int32 strideBytes, System.IntPtr ptr);
```

- `public SetIndices(System.ReadOnlySpan<System.Int32> data) : System.Void`  

```csharp
public System.Void SetIndices(System.ReadOnlySpan<System.Int32> data);
```

- `public SetSkinning(System.Int32 bonesPerVertex, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<System.Single> weights) : System.Void`  

```csharp
public System.Void SetSkinning(System.Int32 bonesPerVertex, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<System.Single> weights);
```

- `public SetSkinning(System.Int32 vertexCount, System.Int32 bonesPerVertex, System.Void* indices, System.Void* weights) : System.Void`  

```csharp
public System.Void SetSkinning(System.Int32 vertexCount, System.Int32 bonesPerVertex, System.Void* indices, System.Void* weights);
```

- `public SetTriangleMaterialIDs(System.ReadOnlySpan<System.Int32> data) : System.Void`  

```csharp
public System.Void SetTriangleMaterialIDs(System.ReadOnlySpan<System.Int32> data);
```

- `public SetTriangleSubMeshIDs(System.ReadOnlySpan<System.Int32> data) : System.Void`  

```csharp
public System.Void SetTriangleSubMeshIDs(System.ReadOnlySpan<System.Int32> data);
```


