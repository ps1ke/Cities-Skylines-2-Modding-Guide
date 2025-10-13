# Colossal.IO.AssetDatabase.GeometryAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Geometry>`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Mesh[]>`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public class GeometryAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Geometry>, Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Mesh[]>
{
    private UnityEngine.Mesh[] m_Instances;
    private System.Int32 m_InstanceRefCount;
    private Colossal.IO.AssetDatabase.GeometryAsset+Data m_Data;
    private System.Int32 mRequestCounts;
    private Colossal.IO.AssetDatabase.GeometryAsset+Loading m_Loading;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromGeometry;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromMeshes;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfEncodeShapeData;
    public static const System.String kExtension;
    public static const System.UInt16 kFormatVersion;
    internal static const System.UInt32 kFileFlagCompressedMeshOpt;
    internal static const System.UInt32 kFileFlagCompressedZstd;
    internal static const System.UInt32 kFileShapeCountMask;
    internal static const System.Int32 kFileShapeCountShift;
    internal static const System.UInt32 kFileShapeFormatMask;
    private static const System.UInt32 kFileShapeFormatNone;
    private static const System.UInt32 kFileShapeFormatPos12Nor9Fixed;
    internal static const System.UInt32 kMeshFlag32BitIndices;
    internal static const System.Int32 kMaxAttributes;

    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.Int32 meshCount { get; }
    public System.Int64 compressedDataSize { get; }
    public System.Int32 shapeCount { get; }
    public System.Int64 shapeDataSize { get; }
    public System.Int64 shapeCompressedDataSize { get; }
    public Unity.Collections.NativeArray<System.Byte> shapeDataBuffer { get; }
    public Colossal.IO.AssetDatabase.GeometryAsset+Data& data { get; }
    public Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading { get; }

    public GeometryAsset();

    private System.Void <ObtainMeshes>b__60_0(System.TimeSpan t);
    private System.Void <Save>b__59_0(System.TimeSpan t);
    private static System.Int32 CalcShapeElementSize(System.UInt32 formatFlags);
    public static System.Void CompleteAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    public static System.Void CompleteLoadingHeaderAsync(System.Int64 fileInfoOffset, System.Int64 fileInfoSize, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    public Unity.Collections.NativeArray<System.Int32> ConvertAllIndicesTo32(Unity.Collections.Allocator allocator);
    public static Unity.Collections.NativeArray<System.Int32> ConvertAllIndicesTo32(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Unity.Collections.Allocator allocator);
    private static System.Void CreateDataFromGeometry(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, Colossal.AssetPipeline.Geometry geometry);
    private static System.Void CreateDataFromUnityMeshes(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, UnityEngine.Mesh[] meshInstances);
    private static UnityEngine.Mesh[] CreateMeshes(System.String baseName, Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    private static System.Void DecompressAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    private static System.Void DecompressDataAfterLoad(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    private static System.Void DecompressIndexData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    private static System.Void DecompressShapeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    public Unity.Collections.NativeSlice<System.Byte> GetAllAttributeData(UnityEngine.Rendering.VertexAttribute attr);
    public System.Void GetAllAttributeFormat(UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension);
    public System.Int32 GetAllIndexFormatStride();
    public static System.Int32 GetAllIndexFormatStride(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    public Unity.Collections.NativeArray<System.Byte> GetAllIndices();
    public static Unity.Collections.NativeArray<System.Byte> GetAllIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    public System.Int32 GetAllIndicesCount();
    public static System.Int32 GetAllIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    public System.Int32 GetAllVertexCount();
    public static System.Int32 GetAllVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    public Unity.Collections.NativeSlice<System.Byte> GetAttributeData(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr);
    public static Unity.Collections.NativeSlice<System.Byte> GetAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr);
    public System.Void GetAttributeFormat(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension);
    public static System.Void GetAttributeFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension);
    public UnityEngine.Rendering.IndexFormat GetIndexFormat(System.Int32 meshIndex);
    public static UnityEngine.Rendering.IndexFormat GetIndexFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
    public Unity.Collections.NativeArray<System.Byte> GetIndices(System.Int32 meshIndex);
    public static Unity.Collections.NativeArray<System.Byte> GetIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
    public System.Int32 GetIndicesCount(System.Int32 meshIndex);
    public static System.Int32 GetIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
    public System.Int32 GetShapeDataSize(System.Int32 meshIndex);
    public UnityEngine.Vector3 GetShapeNormalExtent(System.Int32 meshIndex);
    public UnityEngine.Vector3 GetShapePositionExtent(System.Int32 meshIndex);
    public System.Int32 GetShapeStartOffset(System.Int32 meshIndex);
    public System.Int32 GetSubMeshCount(System.Int32 meshIndex);
    public UnityEngine.Rendering.SubMeshDescriptor GetSubMeshDesc(System.Int32 meshIndex, System.Int32 subMeshIndex);
    public System.Int32 GetVertexCount(System.Int32 meshIndex);
    public static System.Int32 GetVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
    private static UnityEngine.Mesh[] LoadAndCreateMeshes(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    private static System.Void LoadHeaderSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    private static Unity.IO.LowLevel.Unsafe.ReadHandle LoadingBodyAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.UInt32 loadMask);
    private static Unity.IO.LowLevel.Unsafe.ReadHandle LoadingHeaderAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
    public static System.Void LoadSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    public UnityEngine.Mesh[] ObtainMeshes(System.Boolean keepReadable);
    private static System.Void QuantizeShapeData(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent);
    public static System.Void QuantizeShapeData$BurstManaged(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent);
    private static System.UInt64 QuantizeUnorm(System.Single v, System.Int32 bits);
    public System.Void ReleaseMeshes();
    public System.Void RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, System.UInt32 mask);
    public System.Void RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask);
    public virtual System.Void Save(System.Boolean force);
    public System.Void SetData(Colossal.AssetPipeline.Geometry geometry);
    public System.Void SetData(UnityEngine.Mesh[] mesh);
    public static System.Void StartAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    public static System.Boolean StartLoadingBodyAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    public static System.Void StartLoadingHeaderAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
    public virtual System.Void Unload(System.Boolean force);
    public System.Void UnloadPartial(System.Boolean force);
}
```


## Fields

- `private UnityEngine.Mesh[] m_Instances`  

```csharp
private UnityEngine.Mesh[] m_Instances;
```

- `private System.Int32 m_InstanceRefCount`  

```csharp
private System.Int32 m_InstanceRefCount;
```

- `private Colossal.IO.AssetDatabase.GeometryAsset+Data m_Data`  

```csharp
private Colossal.IO.AssetDatabase.GeometryAsset+Data m_Data;
```

- `private System.Int32 mRequestCounts`  

```csharp
private System.Int32 mRequestCounts;
```

- `private Colossal.IO.AssetDatabase.GeometryAsset+Loading m_Loading`  

```csharp
private Colossal.IO.AssetDatabase.GeometryAsset+Loading m_Loading;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromGeometry`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromGeometry;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromMeshes`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromMeshes;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfEncodeShapeData`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfEncodeShapeData;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `public static const System.UInt16 kFormatVersion`  

```csharp
public static const System.UInt16 kFormatVersion;
```

- `internal static const System.UInt32 kFileFlagCompressedMeshOpt`  

```csharp
internal static const System.UInt32 kFileFlagCompressedMeshOpt;
```

- `internal static const System.UInt32 kFileFlagCompressedZstd`  

```csharp
internal static const System.UInt32 kFileFlagCompressedZstd;
```

- `internal static const System.UInt32 kFileShapeCountMask`  

```csharp
internal static const System.UInt32 kFileShapeCountMask;
```

- `internal static const System.Int32 kFileShapeCountShift`  

```csharp
internal static const System.Int32 kFileShapeCountShift;
```

- `internal static const System.UInt32 kFileShapeFormatMask`  

```csharp
internal static const System.UInt32 kFileShapeFormatMask;
```

- `private static const System.UInt32 kFileShapeFormatNone`  

```csharp
private static const System.UInt32 kFileShapeFormatNone;
```

- `private static const System.UInt32 kFileShapeFormatPos12Nor9Fixed`  

```csharp
private static const System.UInt32 kFileShapeFormatPos12Nor9Fixed;
```

- `internal static const System.UInt32 kMeshFlag32BitIndices`  

```csharp
internal static const System.UInt32 kMeshFlag32BitIndices;
```

- `internal static const System.Int32 kMaxAttributes`  

```csharp
internal static const System.Int32 kMaxAttributes;
```


## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```

- `public System.Int32 meshCount { get }`  

```csharp
public System.Int32 meshCount { get; }
```

- `public System.Int64 compressedDataSize { get }`  

```csharp
public System.Int64 compressedDataSize { get; }
```

- `public System.Int32 shapeCount { get }`  

```csharp
public System.Int32 shapeCount { get; }
```

- `public System.Int64 shapeDataSize { get }`  

```csharp
public System.Int64 shapeDataSize { get; }
```

- `public System.Int64 shapeCompressedDataSize { get }`  

```csharp
public System.Int64 shapeCompressedDataSize { get; }
```

- `public Unity.Collections.NativeArray<System.Byte> shapeDataBuffer { get }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> shapeDataBuffer { get; }
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+Data& data { get }`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+Data& data { get; }
```

- `public Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading { get }`  

```csharp
public Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading { get; }
```


## Constructors

- `public GeometryAsset()`  

```csharp
public GeometryAsset();
```


## Methods

- `private <ObtainMeshes>b__60_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <ObtainMeshes>b__60_0(System.TimeSpan t);
```

- `private <Save>b__59_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__59_0(System.TimeSpan t);
```

- `private static CalcShapeElementSize(System.UInt32 formatFlags) : System.Int32`  

```csharp
private static System.Int32 CalcShapeElementSize(System.UInt32 formatFlags);
```

- `public static CompleteAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  

```csharp
public static System.Void CompleteAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `public static CompleteLoadingHeaderAsync(System.Int64 fileInfoOffset, System.Int64 fileInfoSize, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  

```csharp
public static System.Void CompleteLoadingHeaderAsync(System.Int64 fileInfoOffset, System.Int64 fileInfoSize, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `public ConvertAllIndicesTo32(Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public Unity.Collections.NativeArray<System.Int32> ConvertAllIndicesTo32(Unity.Collections.Allocator allocator);
```

- `public static ConvertAllIndicesTo32(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public static Unity.Collections.NativeArray<System.Int32> ConvertAllIndicesTo32(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Unity.Collections.Allocator allocator);
```

- `private static CreateDataFromGeometry(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, Colossal.AssetPipeline.Geometry geometry) : System.Void`  

```csharp
private static System.Void CreateDataFromGeometry(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, Colossal.AssetPipeline.Geometry geometry);
```

- `private static CreateDataFromUnityMeshes(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, UnityEngine.Mesh[] meshInstances) : System.Void`  

```csharp
private static System.Void CreateDataFromUnityMeshes(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, UnityEngine.Mesh[] meshInstances);
```

- `private static CreateMeshes(System.String baseName, Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : UnityEngine.Mesh[]`  

```csharp
private static UnityEngine.Mesh[] CreateMeshes(System.String baseName, Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `private static DecompressAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  

```csharp
private static System.Void DecompressAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `private static DecompressDataAfterLoad(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  

```csharp
private static System.Void DecompressDataAfterLoad(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `private static DecompressIndexData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  

```csharp
private static System.Void DecompressIndexData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `private static DecompressShapeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  

```csharp
private static System.Void DecompressShapeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `public GetAllAttributeData(UnityEngine.Rendering.VertexAttribute attr) : Unity.Collections.NativeSlice<System.Byte>`  

```csharp
public Unity.Collections.NativeSlice<System.Byte> GetAllAttributeData(UnityEngine.Rendering.VertexAttribute attr);
```

- `public GetAllAttributeFormat(UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension) : System.Void`  

```csharp
public System.Void GetAllAttributeFormat(UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension);
```

- `public GetAllIndexFormatStride() : System.Int32`  

```csharp
public System.Int32 GetAllIndexFormatStride();
```

- `public static GetAllIndexFormatStride(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Int32`  

```csharp
public static System.Int32 GetAllIndexFormatStride(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `public GetAllIndices() : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetAllIndices();
```

- `public static GetAllIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public static Unity.Collections.NativeArray<System.Byte> GetAllIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `public GetAllIndicesCount() : System.Int32`  

```csharp
public System.Int32 GetAllIndicesCount();
```

- `public static GetAllIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Int32`  

```csharp
public static System.Int32 GetAllIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `public GetAllVertexCount() : System.Int32`  

```csharp
public System.Int32 GetAllVertexCount();
```

- `public static GetAllVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Int32`  

```csharp
public static System.Int32 GetAllVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `public GetAttributeData(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr) : Unity.Collections.NativeSlice<System.Byte>`  

```csharp
public Unity.Collections.NativeSlice<System.Byte> GetAttributeData(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr);
```

- `public static GetAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr) : Unity.Collections.NativeSlice<System.Byte>`  

```csharp
public static Unity.Collections.NativeSlice<System.Byte> GetAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr);
```

- `public GetAttributeFormat(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension) : System.Void`  

```csharp
public System.Void GetAttributeFormat(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension);
```

- `public static GetAttributeFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension) : System.Void`  

```csharp
public static System.Void GetAttributeFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension);
```

- `public GetIndexFormat(System.Int32 meshIndex) : UnityEngine.Rendering.IndexFormat`  

```csharp
public UnityEngine.Rendering.IndexFormat GetIndexFormat(System.Int32 meshIndex);
```

- `public static GetIndexFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : UnityEngine.Rendering.IndexFormat`  

```csharp
public static UnityEngine.Rendering.IndexFormat GetIndexFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
```

- `public GetIndices(System.Int32 meshIndex) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetIndices(System.Int32 meshIndex);
```

- `public static GetIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public static Unity.Collections.NativeArray<System.Byte> GetIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
```

- `public GetIndicesCount(System.Int32 meshIndex) : System.Int32`  

```csharp
public System.Int32 GetIndicesCount(System.Int32 meshIndex);
```

- `public static GetIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : System.Int32`  

```csharp
public static System.Int32 GetIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
```

- `public GetShapeDataSize(System.Int32 meshIndex) : System.Int32`  

```csharp
public System.Int32 GetShapeDataSize(System.Int32 meshIndex);
```

- `public GetShapeNormalExtent(System.Int32 meshIndex) : UnityEngine.Vector3`  

```csharp
public UnityEngine.Vector3 GetShapeNormalExtent(System.Int32 meshIndex);
```

- `public GetShapePositionExtent(System.Int32 meshIndex) : UnityEngine.Vector3`  

```csharp
public UnityEngine.Vector3 GetShapePositionExtent(System.Int32 meshIndex);
```

- `public GetShapeStartOffset(System.Int32 meshIndex) : System.Int32`  

```csharp
public System.Int32 GetShapeStartOffset(System.Int32 meshIndex);
```

- `public GetSubMeshCount(System.Int32 meshIndex) : System.Int32`  

```csharp
public System.Int32 GetSubMeshCount(System.Int32 meshIndex);
```

- `public GetSubMeshDesc(System.Int32 meshIndex, System.Int32 subMeshIndex) : UnityEngine.Rendering.SubMeshDescriptor`  

```csharp
public UnityEngine.Rendering.SubMeshDescriptor GetSubMeshDesc(System.Int32 meshIndex, System.Int32 subMeshIndex);
```

- `public GetVertexCount(System.Int32 meshIndex) : System.Int32`  

```csharp
public System.Int32 GetVertexCount(System.Int32 meshIndex);
```

- `public static GetVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : System.Int32`  

```csharp
public static System.Int32 GetVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex);
```

- `private static LoadAndCreateMeshes(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : UnityEngine.Mesh[]`  

```csharp
private static UnityEngine.Mesh[] LoadAndCreateMeshes(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `private static LoadHeaderSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  

```csharp
private static System.Void LoadHeaderSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `private static LoadingBodyAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.UInt32 loadMask) : Unity.IO.LowLevel.Unsafe.ReadHandle`  

```csharp
private static Unity.IO.LowLevel.Unsafe.ReadHandle LoadingBodyAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.UInt32 loadMask);
```

- `private static LoadingHeaderAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : Unity.IO.LowLevel.Unsafe.ReadHandle`  

```csharp
private static Unity.IO.LowLevel.Unsafe.ReadHandle LoadingHeaderAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data);
```

- `public static LoadSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  

```csharp
public static System.Void LoadSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `public ObtainMeshes(System.Boolean keepReadable = False) : UnityEngine.Mesh[]`  

```csharp
public UnityEngine.Mesh[] ObtainMeshes(System.Boolean keepReadable);
```

- `private static QuantizeShapeData(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent) : System.Void`  

```csharp
private static System.Void QuantizeShapeData(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent);
```

- `public static QuantizeShapeData$BurstManaged(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent) : System.Void`  

```csharp
public static System.Void QuantizeShapeData$BurstManaged(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent);
```

- `private static QuantizeUnorm(System.Single v, System.Int32 bits) : System.UInt64`  

```csharp
private static System.UInt64 QuantizeUnorm(System.Single v, System.Int32 bits);
```

- `public ReleaseMeshes() : System.Void`  

```csharp
public System.Void ReleaseMeshes();
```

- `public RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, System.UInt32 mask) : System.Void`  

```csharp
public System.Void RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, System.UInt32 mask);
```

- `public RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask) : System.Void`  

```csharp
public System.Void RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask);
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public SetData(Colossal.AssetPipeline.Geometry geometry) : System.Void`  

```csharp
public System.Void SetData(Colossal.AssetPipeline.Geometry geometry);
```

- `public SetData(UnityEngine.Mesh[] mesh = null) : System.Void`  

```csharp
public System.Void SetData(UnityEngine.Mesh[] mesh);
```

- `public static StartAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  

```csharp
public static System.Void StartAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `public static StartLoadingBodyAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Boolean`  

```csharp
public static System.Boolean StartLoadingBodyAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `public static StartLoadingHeaderAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  

```csharp
public static System.Void StartLoadingHeaderAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```

- `public UnloadPartial(System.Boolean force = False) : System.Void`  

```csharp
public System.Void UnloadPartial(System.Boolean force);
```


## Nested types

- `Colossal.IO.AssetDatabase.GeometryAsset+Attribute`  
- `Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader`  
- `Colossal.IO.AssetDatabase.GeometryAsset+SubMeshInfo`  
- `Colossal.IO.AssetDatabase.GeometryAsset+MeshDataOffsets`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Data`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Loading`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Colossal.IO.AssetDatabase.QuantizeShapeData_00000131$PostfixBurstDelegate`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Colossal.IO.AssetDatabase.QuantizeShapeData_00000131$BurstDirectCall`  

