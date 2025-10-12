# Colossal.AssetPipeline.Importers.ModelImporter+Model

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Fields

- `public System.Action<UnityEngine.GameObject> OnPostDebugOutput`  
- `private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField`  
- `public readonly System.String name`  
- `public readonly UnityEngine.Matrix4x4 transform`  
- `public System.Int32 vertexCount`  
- `public readonly Unity.Collections.NativeArray<System.Int32> indices`  
- `private Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData`  
- `public readonly UnityEngine.Rendering.SubMeshDescriptor[] subMeshes`  
- `public System.Int32 rootBoneIndex`  
- `public Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones`  
- `private Unity.Collections.NativeArray<System.Byte> <shapeData>k__BackingField`  
- `private System.Int32 <shapeCount>k__BackingField`  
- `public UnityEngine.Mesh m_CachedObject`  

## Properties

- `public System.Boolean hasSkin { get }`  
- `public System.Boolean isValid { get }`  
- `public Colossal.AssetPipeline.IAsset sourceAsset { get; set }`  
- `public Unity.Collections.NativeArray<System.Byte> shapeData { get; private set }`  
- `public System.Int32 shapeCount { get; private set }`  
- `public System.Int32 indexCount { get }`  
- `public System.Int32 subMeshCount { get }`  
- `public System.Int32 attributesCount { get }`  

## Constructors

- `public Model(System.String name, UnityEngine.Matrix4x4 transform, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData, UnityEngine.Rendering.SubMeshDescriptor[] subMeshes, System.Int32 rootBoneIndex, Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo[] bones)`  

## Methods

- `public AddOrGetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension, Unity.Collections.NativeArrayOptions allocOptions = UninitializedMemory) : Unity.Collections.NativeArray<T>`  
- `public static CreateSubMesh(System.String name, System.Int32 indexCount, System.Int32 vertexCount, Unity.Collections.NativeArray<System.Int32> indices, Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData[] vertexData) : UnityEngine.Rendering.SubMeshDescriptor`  
- `public Dispose() : System.Void`  
- `public GetAttribute<T>(UnityEngine.Rendering.VertexAttribute attribute, UnityEngine.Rendering.VertexAttributeFormat convertFormat = Float32, System.Int32 convertDimension = 4) : Unity.Collections.NativeArray<T>`  
- `public GetAttributeData(UnityEngine.Rendering.VertexAttribute attribute) : Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData`  
- `public GetAttributeReadOnlyPtr(UnityEngine.Rendering.VertexAttribute attribute) : System.IntPtr`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData>`  
- `public GetIndices(System.Int32 subMesh) : Unity.Collections.NativeSlice<System.Int32>`  
- `public GetIndicesAsSpan(System.Int32 subMesh) : System.ReadOnlySpan<System.Int32>`  
- `public GetIndicesReadOnlyPtr() : System.IntPtr`  
- `public HasAttribute(UnityEngine.Rendering.VertexAttribute attribute) : System.Boolean`  
- `public RemoveAttribute(UnityEngine.Rendering.VertexAttribute attribute) : System.Boolean`  
- `public ReplaceAttribute(Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData data) : System.Void`  
- `public SetShapeData(Unity.Collections.NativeArray<System.Byte> data, System.Int32 count) : System.Void`  
- `public SplitBySubMeshes() : Colossal.AssetPipeline.Importers.ModelImporter+Model[]`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public ToUnityMesh(System.Boolean hideAndDontSave = True) : UnityEngine.Mesh`  
- `public ValidateAttributes() : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.Importers.ModelImporter+Model+VertexData`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model+BoneInfo`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model+<>c`  
- `Colossal.AssetPipeline.Importers.ModelImporter+Model+<>c__DisplayClass48_0`  

