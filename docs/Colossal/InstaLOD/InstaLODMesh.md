# Colossal.InstaLOD.InstaLODMesh

**Assembly:** `InstaLOD.Runtime`  
**Namespace:** `Colossal.InstaLOD`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `internal System.IntPtr m_Ptr`  
- `private Colossal.InstaLOD.InstaLODSDK m_SDK`  

## Properties

- `public System.Boolean isValid { get }`  
- `public System.Int32 calcSubMeshCount { get }`  

## Constructors

- `public InstaLODMesh(Colossal.InstaLOD.InstaLODSDK sdk)`  

## Methods

- `public Append(Colossal.InstaLOD.InstaLODMesh meshToAppend) : System.Void`  
- `public CheckAndSanitize() : System.Void`  
- `public Clear() : System.Void`  
- `public Dispose() : System.Void`  
- `public ExtractSubMesh(System.Int32 id) : Colossal.InstaLOD.InstaLODMesh`  
- `public GetData() : Colossal.InstaLOD.MeshData`  
- `public SetAttribute<T>(UnityEngine.Rendering.VertexAttribute attr, System.ReadOnlySpan<T> data) : System.Void`  
- `public SetAttribute(UnityEngine.Rendering.VertexAttribute attr, System.Int32 count, System.Int32 strideBytes, System.IntPtr ptr) : System.Void`  
- `public SetIndices(System.ReadOnlySpan<System.Int32> data) : System.Void`  
- `public SetSkinning(System.Int32 bonesPerVertex, System.ReadOnlySpan<System.Int32> indices, System.ReadOnlySpan<System.Single> weights) : System.Void`  
- `public SetSkinning(System.Int32 vertexCount, System.Int32 bonesPerVertex, System.Void* indices, System.Void* weights) : System.Void`  
- `public SetTriangleMaterialIDs(System.ReadOnlySpan<System.Int32> data) : System.Void`  
- `public SetTriangleSubMeshIDs(System.ReadOnlySpan<System.Int32> data) : System.Void`  

