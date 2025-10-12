# Colossal.IO.AssetDatabase.GeometryAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Geometry>`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Mesh[]>`  

**Attributes:** `BurstCompile`  

## Fields

- `private UnityEngine.Mesh[] m_Instances`  
- `private System.Int32 m_InstanceRefCount`  
- `private Colossal.IO.AssetDatabase.GeometryAsset+Data m_Data`  
- `private System.Int32 mRequestCounts`  
- `private Colossal.IO.AssetDatabase.GeometryAsset+Loading m_Loading`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromGeometry`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCreateFromMeshes`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfEncodeShapeData`  
- `public static const System.String kExtension`  
- `public static const System.UInt16 kFormatVersion`  
- `internal static const System.UInt32 kFileFlagCompressedMeshOpt`  
- `internal static const System.UInt32 kFileFlagCompressedZstd`  
- `internal static const System.UInt32 kFileShapeCountMask`  
- `internal static const System.Int32 kFileShapeCountShift`  
- `internal static const System.UInt32 kFileShapeFormatMask`  
- `private static const System.UInt32 kFileShapeFormatNone`  
- `private static const System.UInt32 kFileShapeFormatPos12Nor9Fixed`  
- `internal static const System.UInt32 kMeshFlag32BitIndices`  
- `internal static const System.Int32 kMaxAttributes`  

## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.Int32 meshCount { get }`  
- `public System.Int64 compressedDataSize { get }`  
- `public System.Int32 shapeCount { get }`  
- `public System.Int64 shapeDataSize { get }`  
- `public System.Int64 shapeCompressedDataSize { get }`  
- `public Unity.Collections.NativeArray<System.Byte> shapeDataBuffer { get }`  
- `public Colossal.IO.AssetDatabase.GeometryAsset+Data& data { get }`  
- `public Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading { get }`  

## Constructors

- `public GeometryAsset()`  

## Methods

- `private <ObtainMeshes>b__60_0(System.TimeSpan t) : System.Void`  
- `private <Save>b__59_0(System.TimeSpan t) : System.Void`  
- `private static CalcShapeElementSize(System.UInt32 formatFlags) : System.Int32`  
- `public static CompleteAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  
- `public static CompleteLoadingHeaderAsync(System.Int64 fileInfoOffset, System.Int64 fileInfoSize, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  
- `public ConvertAllIndicesTo32(Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<System.Int32>`  
- `public static ConvertAllIndicesTo32(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<System.Int32>`  
- `private static CreateDataFromGeometry(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, Colossal.AssetPipeline.Geometry geometry) : System.Void`  
- `private static CreateDataFromUnityMeshes(Colossal.IO.AssetDatabase.GeometryAsset+Data& outData, UnityEngine.Mesh[] meshInstances) : System.Void`  
- `private static CreateMeshes(System.String baseName, Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : UnityEngine.Mesh[]`  
- `private static DecompressAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  
- `private static DecompressDataAfterLoad(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  
- `private static DecompressIndexData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  
- `private static DecompressShapeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Void`  
- `public GetAllAttributeData(UnityEngine.Rendering.VertexAttribute attr) : Unity.Collections.NativeSlice<System.Byte>`  
- `public GetAllAttributeFormat(UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension) : System.Void`  
- `public GetAllIndexFormatStride() : System.Int32`  
- `public static GetAllIndexFormatStride(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Int32`  
- `public GetAllIndices() : Unity.Collections.NativeArray<System.Byte>`  
- `public static GetAllIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetAllIndicesCount() : System.Int32`  
- `public static GetAllIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Int32`  
- `public GetAllVertexCount() : System.Int32`  
- `public static GetAllVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : System.Int32`  
- `public GetAttributeData(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr) : Unity.Collections.NativeSlice<System.Byte>`  
- `public static GetAttributeData(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr) : Unity.Collections.NativeSlice<System.Byte>`  
- `public GetAttributeFormat(System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension) : System.Void`  
- `public static GetAttributeFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex, UnityEngine.Rendering.VertexAttribute attr, UnityEngine.Rendering.VertexAttributeFormat& format, System.Int32& dimension) : System.Void`  
- `public GetIndexFormat(System.Int32 meshIndex) : UnityEngine.Rendering.IndexFormat`  
- `public static GetIndexFormat(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : UnityEngine.Rendering.IndexFormat`  
- `public GetIndices(System.Int32 meshIndex) : Unity.Collections.NativeArray<System.Byte>`  
- `public static GetIndices(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetIndicesCount(System.Int32 meshIndex) : System.Int32`  
- `public static GetIndicesCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : System.Int32`  
- `public GetShapeDataSize(System.Int32 meshIndex) : System.Int32`  
- `public GetShapeNormalExtent(System.Int32 meshIndex) : UnityEngine.Vector3`  
- `public GetShapePositionExtent(System.Int32 meshIndex) : UnityEngine.Vector3`  
- `public GetShapeStartOffset(System.Int32 meshIndex) : System.Int32`  
- `public GetSubMeshCount(System.Int32 meshIndex) : System.Int32`  
- `public GetSubMeshDesc(System.Int32 meshIndex, System.Int32 subMeshIndex) : UnityEngine.Rendering.SubMeshDescriptor`  
- `public GetVertexCount(System.Int32 meshIndex) : System.Int32`  
- `public static GetVertexCount(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.Int32 meshIndex) : System.Int32`  
- `private static LoadAndCreateMeshes(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : UnityEngine.Mesh[]`  
- `private static LoadHeaderSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  
- `private static LoadingBodyAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, System.UInt32 loadMask) : Unity.IO.LowLevel.Unsafe.ReadHandle`  
- `private static LoadingHeaderAsync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, Colossal.IO.AssetDatabase.GeometryAsset+Data& data) : Unity.IO.LowLevel.Unsafe.ReadHandle`  
- `public static LoadSync(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask, Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  
- `public ObtainMeshes(System.Boolean keepReadable = False) : UnityEngine.Mesh[]`  
- `private static QuantizeShapeData(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent) : System.Void`  
- `public static QuantizeShapeData$BurstManaged(Unity.Collections.NativeArray`1[[System.ValueTuple`2[[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null],[Unity.Mathematics.float3, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]], System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& inData, Unity.Collections.NativeArray`1[[System.UInt64, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& outData, Unity.Mathematics.float3& positionExtent, Unity.Mathematics.float3& normalExtent) : System.Void`  
- `private static QuantizeUnorm(System.Single v, System.Int32 bits) : System.UInt64`  
- `public ReleaseMeshes() : System.Void`  
- `public RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, System.UInt32 mask) : System.Void`  
- `public RequestDataAsync(Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem loadingSystem, Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.UInt32 mask) : System.Void`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public SetData(Colossal.AssetPipeline.Geometry geometry) : System.Void`  
- `public SetData(UnityEngine.Mesh[] mesh = null) : System.Void`  
- `public static StartAsyncLoading(Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  
- `public static StartLoadingBodyAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Boolean`  
- `public static StartLoadingHeaderAsync(Colossal.IO.AssetDatabase.GeometryAsset+Data& data, Colossal.IO.AssetDatabase.GeometryAsset+Loading& loading) : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  
- `public UnloadPartial(System.Boolean force = False) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.GeometryAsset+Attribute`  
- `Colossal.IO.AssetDatabase.GeometryAsset+MeshInfoHeader`  
- `Colossal.IO.AssetDatabase.GeometryAsset+SubMeshInfo`  
- `Colossal.IO.AssetDatabase.GeometryAsset+MeshDataOffsets`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Data`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Loading`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Colossal.IO.AssetDatabase.QuantizeShapeData_00000131$PostfixBurstDelegate`  
- `Colossal.IO.AssetDatabase.GeometryAsset+Colossal.IO.AssetDatabase.QuantizeShapeData_00000131$BurstDirectCall`  

