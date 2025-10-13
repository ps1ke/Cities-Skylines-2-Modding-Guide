# Colossal.AssetPipeline.Importers.ModelImporter+Model

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Code

```csharp
public class Model : System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>, System.Collections.IEnumerable, System.IDisposable
{
    public System.Action<UnityEngine.GameObject> OnPostDebugOutput;
    private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField;
    public readonly System.String name;
    public readonly UnityEngine.Matrix4x4 transform;
    public System.Int32 vertexCount;
    public readonly Unity.Collections.NativeArray<System.Int32> indices;
    private Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData;
    public readonly UnityEngine.Rendering.SubMeshDescriptor[] subMeshes;
    public System.Int32 rootBoneIndex;
    public Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones;
    private Unity.Collections.NativeArray<System.Byte> <shapeData>k__BackingField;
    private System.Int32 <shapeCount>k__BackingField;
    public UnityEngine.Mesh m_CachedObject;

    public System.Boolean hasSkin { get; }
    public System.Boolean isValid { get; }
    public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }
    public Unity.Collections.NativeArray<System.Byte> shapeData { get; private set; }
    public System.Int32 shapeCount { get; private set; }
    public System.Int32 indexCount { get; }
    public System.Int32 subMeshCount { get; }
    public System.Int32 attributesCount { get; }

    public Model(System.String name, UnityEngine.Matrix4x4 transform, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData, UnityEngine.Rendering.SubMeshDescriptor[] subMeshes, System.Int32 rootBoneIndex, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones);

    public Unity.Collections.NativeArray<T> AddOrGetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArrayOptions allocOptions);
    public static UnityEngine.Rendering.SubMeshDescriptor CreateSubMesh(System.String name, System.Int32 indexCount, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData);
    public System.Void Dispose();
    public Unity.Collections.NativeArray<T> GetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat convertFormat, System.Int32 convertDimension);
    public Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData GetAttributeData(UnityEngine.Rendering.VertexAttribute attribute);
    public System.IntPtr GetAttributeReadOnlyPtr(UnityEngine.Rendering.VertexAttribute attribute);
    public System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData> GetEnumerator();
    public Unity.Collections.NativeSlice<System.Int32> GetIndices(System.Int32 subMesh);
    public System.ReadOnlySpan<System.Int32> GetIndicesAsSpan(System.Int32 subMesh);
    public System.IntPtr GetIndicesReadOnlyPtr();
    public System.Boolean HasAttribute(UnityEngine.Rendering.VertexAttribute attribute);
    public System.Boolean RemoveAttribute(UnityEngine.Rendering.VertexAttribute attribute);
    public System.Void ReplaceAttribute(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData data);
    public System.Void SetShapeData(Unity.Collections.NativeArray<System.Byte> data, System.Int32 count);
    public Colossal.AssetPipeline.Importers.ModelImporter+Model[] SplitBySubMeshes();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public UnityEngine.Mesh ToUnityMesh(System.Boolean hideAndDontSave);
    public System.Boolean ValidateAttributes();
}
```


## Fields

- `public System.Action<UnityEngine.GameObject> OnPostDebugOutput`  

```csharp
public System.Action<UnityEngine.GameObject> OnPostDebugOutput;
```

- `private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField`  

```csharp
private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField;
```

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `public readonly UnityEngine.Matrix4x4 transform`  

```csharp
public readonly UnityEngine.Matrix4x4 transform;
```

- `public System.Int32 vertexCount`  

```csharp
public System.Int32 vertexCount;
```

- `public readonly Unity.Collections.NativeArray<System.Int32> indices`  

```csharp
public readonly Unity.Collections.NativeArray<System.Int32> indices;
```

- `private Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData`  

```csharp
private Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData;
```

- `public readonly UnityEngine.Rendering.SubMeshDescriptor[] subMeshes`  

```csharp
public readonly UnityEngine.Rendering.SubMeshDescriptor[] subMeshes;
```

- `public System.Int32 rootBoneIndex`  

```csharp
public System.Int32 rootBoneIndex;
```

- `public Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones`  

```csharp
public Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones;
```

- `private Unity.Collections.NativeArray<System.Byte> <shapeData>k__BackingField`  

```csharp
private Unity.Collections.NativeArray<System.Byte> <shapeData>k__BackingField;
```

- `private System.Int32 <shapeCount>k__BackingField`  

```csharp
private System.Int32 <shapeCount>k__BackingField;
```

- `public UnityEngine.Mesh m_CachedObject`  

```csharp
public UnityEngine.Mesh m_CachedObject;
```


## Properties

- `public System.Boolean hasSkin { get }`  

```csharp
public System.Boolean hasSkin { get; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public Colossal.AssetPipeline.IAsset sourceAsset { get; set }`  

```csharp
public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }
```

- `public Unity.Collections.NativeArray<System.Byte> shapeData { get; private set }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> shapeData { get; private set; }
```

- `public System.Int32 shapeCount { get; private set }`  

```csharp
public System.Int32 shapeCount { get; private set; }
```

- `public System.Int32 indexCount { get }`  

```csharp
public System.Int32 indexCount { get; }
```

- `public System.Int32 subMeshCount { get }`  

```csharp
public System.Int32 subMeshCount { get; }
```

- `public System.Int32 attributesCount { get }`  

```csharp
public System.Int32 attributesCount { get; }
```


## Constructors

- `public Model(System.String name, UnityEngine.Matrix4x4 transform, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData, UnityEngine.Rendering.SubMeshDescriptor[] subMeshes, System.Int32 rootBoneIndex, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones)`  

```csharp
public Model(System.String name, UnityEngine.Matrix4x4 transform, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData, UnityEngine.Rendering.SubMeshDescriptor[] subMeshes, System.Int32 rootBoneIndex, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones);
```


## Methods

- `public AddOrGetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArrayOptions allocOptions = UninitializedMemory) : Unity.Collections.NativeArray<T>`  

```csharp
public Unity.Collections.NativeArray<T> AddOrGetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArrayOptions allocOptions);
```

- `public static CreateSubMesh(System.String name, System.Int32 indexCount, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData) : UnityEngine.Rendering.SubMeshDescriptor`  

```csharp
public static UnityEngine.Rendering.SubMeshDescriptor CreateSubMesh(System.String name, System.Int32 indexCount, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat convertFormat = Float32, System.Int32 convertDimension = 4) : Unity.Collections.NativeArray<T>`  

```csharp
public Unity.Collections.NativeArray<T> GetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat convertFormat, System.Int32 convertDimension);
```

- `public GetAttributeData(UnityEngine.Rendering.VertexAttribute attribute) : Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData`  

```csharp
public Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData GetAttributeData(UnityEngine.Rendering.VertexAttribute attribute);
```

- `public GetAttributeReadOnlyPtr(UnityEngine.Rendering.VertexAttribute attribute) : System.IntPtr`  

```csharp
public System.IntPtr GetAttributeReadOnlyPtr(UnityEngine.Rendering.VertexAttribute attribute);
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>`  

```csharp
public System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData> GetEnumerator();
```

- `public GetIndices(System.Int32 subMesh) : Unity.Collections.NativeSlice<System.Int32>`  

```csharp
public Unity.Collections.NativeSlice<System.Int32> GetIndices(System.Int32 subMesh);
```

- `public GetIndicesAsSpan(System.Int32 subMesh) : System.ReadOnlySpan<System.Int32>`  

```csharp
public System.ReadOnlySpan<System.Int32> GetIndicesAsSpan(System.Int32 subMesh);
```

- `public GetIndicesReadOnlyPtr() : System.IntPtr`  

```csharp
public System.IntPtr GetIndicesReadOnlyPtr();
```

- `public HasAttribute(UnityEngine.Rendering.VertexAttribute attribute) : System.Boolean`  

```csharp
public System.Boolean HasAttribute(UnityEngine.Rendering.VertexAttribute attribute);
```

- `public RemoveAttribute(UnityEngine.Rendering.VertexAttribute attribute) : System.Boolean`  

```csharp
public System.Boolean RemoveAttribute(UnityEngine.Rendering.VertexAttribute attribute);
```

- `public ReplaceAttribute(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData data) : System.Void`  

```csharp
public System.Void ReplaceAttribute(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData data);
```

- `public SetShapeData(Unity.Collections.NativeArray<System.Byte> data, System.Int32 count) : System.Void`  

```csharp
public System.Void SetShapeData(Unity.Collections.NativeArray<System.Byte> data, System.Int32 count);
```

- `public SplitBySubMeshes() : Colossal.AssetPipeline.Importers.ModelImporter+Model[]`  

```csharp
public Colossal.AssetPipeline.Importers.ModelImporter+Model[] SplitBySubMeshes();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public ToUnityMesh(System.Boolean hideAndDontSave = True) : UnityEngine.Mesh`  

```csharp
public UnityEngine.Mesh ToUnityMesh(System.Boolean hideAndDontSave);
```

- `public ValidateAttributes() : System.Boolean`  

```csharp
public System.Boolean ValidateAttributes();
```


## Nested types

- `Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model+<>c`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model+<>c__DisplayClass48_0`  

