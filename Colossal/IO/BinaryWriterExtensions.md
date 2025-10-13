# Colossal.IO.BinaryWriterExtensions

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.IO`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class BinaryWriterExtensions
{
    public static System.Collections.Generic.List<System.UInt16> GetUShortIndices(UnityEngine.Mesh mesh, System.Int32 i);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Guid guid);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Type type);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Bounds v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector2 v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector3 v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector4 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float2 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float3 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float4 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.int2 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.int3 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.int4 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint2 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint3 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint4 v);
    public static System.Void Write(System.IO.BinaryWriter sw, Colossal.IO.BinaryWriterExtensions+UInt4 v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Color v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Color32 v);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, System.Single> dic);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, System.Int32> dic);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> dic);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> dic);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.ICollection<System.String> dic);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Type[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector2[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector3[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector4[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Color[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, System.String[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Int32[] v);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.List<System.UInt16> v);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Rendering.SubMeshDescriptor desc);
    public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Rect rect);
    public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> entries);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, System.Int32[] v);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector2[] v);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector3[] v);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector4[] v);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.BoneWeight[] boneWeights, System.Boolean hasWeights, System.Boolean hasIndices);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, Colossal.IO.BinaryWriterExtensions+UInt4[] v);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, System.Collections.Generic.IList<UnityEngine.Vector4> v, System.Int32 dimension);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Color[] v);
    public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Color32[] v);
    public static System.Void WriteDirectAsUShort(System.IO.BinaryWriter sw, System.Int32[] v);
    public static System.Void WriteMeshData(System.IO.BinaryWriter sw, UnityEngine.Mesh mesh);
    public static System.Boolean WriteNull<T>(System.IO.BinaryWriter sw, T v);
    public static System.Void WriteNullableString(System.IO.BinaryWriter sw, System.String v);
}
```


## Methods

- `public static GetUShortIndices(UnityEngine.Mesh mesh, System.Int32 i) : System.Collections.Generic.List<System.UInt16>`  

```csharp
public static System.Collections.Generic.List<System.UInt16> GetUShortIndices(UnityEngine.Mesh mesh, System.Int32 i);
```

- `public static Write(System.IO.BinaryWriter sw, System.Guid guid) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Guid guid);
```

- `public static Write(System.IO.BinaryWriter sw, System.Type type) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Type type);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Bounds v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Bounds v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Vector2 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector2 v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Vector3 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector3 v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Vector4 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector4 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.float2 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float2 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.float3 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float3 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.float4 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.float4 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.int2 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.int2 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.int3 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.int3 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.int4 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.int4 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint2 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint2 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint3 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint3 v);
```

- `public static Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint4 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Unity.Mathematics.uint4 v);
```

- `public static Write(System.IO.BinaryWriter sw, Colossal.IO.BinaryWriterExtensions+UInt4 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, Colossal.IO.BinaryWriterExtensions+UInt4 v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Color v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Color v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Color32 v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Color32 v);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, System.Single> dic) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, System.Single> dic);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, System.Int32> dic) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, System.Int32> dic);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> dic) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> dic);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> dic) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> dic);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.ICollection<System.String> dic) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.ICollection<System.String> dic);
```

- `public static Write(System.IO.BinaryWriter sw, System.Type[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Type[] v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Vector2[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector2[] v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Vector3[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector3[] v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Vector4[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Vector4[] v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Color[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Color[] v);
```

- `public static Write(System.IO.BinaryWriter sw, System.String[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.String[] v);
```

- `public static Write(System.IO.BinaryWriter sw, System.Int32[] v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Int32[] v);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.List<System.UInt16> v) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.List<System.UInt16> v);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Rendering.SubMeshDescriptor desc) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Rendering.SubMeshDescriptor desc);
```

- `public static Write(System.IO.BinaryWriter sw, UnityEngine.Rect rect) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, UnityEngine.Rect rect);
```

- `public static Write(System.IO.BinaryWriter sw, System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> entries) : System.Void`  

```csharp
public static System.Void Write(System.IO.BinaryWriter sw, System.Collections.Generic.IReadOnlyList<UnityEngine.Rect> entries);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, System.Int32[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, System.Int32[] v);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector2[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector2[] v);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector3[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector3[] v);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector4[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Vector4[] v);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, UnityEngine.BoneWeight[] boneWeights, System.Boolean hasWeights, System.Boolean hasIndices) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.BoneWeight[] boneWeights, System.Boolean hasWeights, System.Boolean hasIndices);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, Colossal.IO.BinaryWriterExtensions+UInt4[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, Colossal.IO.BinaryWriterExtensions+UInt4[] v);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, System.Collections.Generic.IList<UnityEngine.Vector4> v, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, System.Collections.Generic.IList<UnityEngine.Vector4> v, System.Int32 dimension);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Color[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Color[] v);
```

- `public static WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Color32[] v) : System.Void`  

```csharp
public static System.Void WriteDirect(System.IO.BinaryWriter sw, UnityEngine.Color32[] v);
```

- `public static WriteDirectAsUShort(System.IO.BinaryWriter sw, System.Int32[] v) : System.Void`  

```csharp
public static System.Void WriteDirectAsUShort(System.IO.BinaryWriter sw, System.Int32[] v);
```

- `public static WriteMeshData(System.IO.BinaryWriter sw, UnityEngine.Mesh mesh) : System.Void`  

```csharp
public static System.Void WriteMeshData(System.IO.BinaryWriter sw, UnityEngine.Mesh mesh);
```

- `public static WriteNull<T>(System.IO.BinaryWriter sw, T v) : System.Boolean`  

```csharp
public static System.Boolean WriteNull<T>(System.IO.BinaryWriter sw, T v);
```

- `public static WriteNullableString(System.IO.BinaryWriter sw, System.String v) : System.Void`  

```csharp
public static System.Void WriteNullableString(System.IO.BinaryWriter sw, System.String v);
```


## Nested types

- `Colossal.IO.BinaryWriterExtensions+UInt4`  

