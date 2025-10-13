# Colossal.IO.BinaryReaderExtensions

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.IO`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class BinaryReaderExtensions
{
    private static System.Int32 kMaxAttributes;

    public static UnityEngine.Bounds ReadBounds(System.IO.BinaryReader sr);
    public static UnityEngine.Color ReadColor(System.IO.BinaryReader sr);
    public static UnityEngine.Color[] ReadColors(System.IO.BinaryReader sr);
    public static Unity.Mathematics.float2 ReadFloat2(System.IO.BinaryReader sr);
    public static Unity.Mathematics.float3 ReadFloat3(System.IO.BinaryReader sr);
    public static Unity.Mathematics.float4 ReadFloat4(System.IO.BinaryReader sr);
    public static System.Guid ReadGuid(System.IO.BinaryReader sr);
    public static Unity.Mathematics.int2 ReadInt2(System.IO.BinaryReader sr);
    public static Unity.Mathematics.int3 ReadInt3(System.IO.BinaryReader sr);
    public static Unity.Mathematics.int4 ReadInt4(System.IO.BinaryReader sr);
    public static System.Int32[] ReadInts(System.IO.BinaryReader sr);
    public static UnityEngine.Rendering.VertexAttribute ReadMeshAttribute(System.IO.BinaryReader sr);
    public static System.Int64 ReadMeshAttributeData(System.IO.BinaryReader sr, UnityEngine.Mesh mesh);
    public static System.Int64 ReadMeshData(System.IO.BinaryReader sr, UnityEngine.Mesh mesh);
    public static System.Boolean ReadNull(System.IO.BinaryReader sr);
    public static System.String ReadNullableString(System.IO.BinaryReader sr);
    public static UnityEngine.Rect ReadRect(System.IO.BinaryReader sr);
    public static System.Collections.Generic.List<UnityEngine.Rect> ReadRectList(System.IO.BinaryReader sr);
    public static System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> ReadStringColorDictionary(System.IO.BinaryReader sr);
    public static System.Collections.Generic.Dictionary<System.String, System.Single> ReadStringFloatDictionary(System.IO.BinaryReader sr);
    public static System.Collections.Generic.HashSet<System.String> ReadStringHashSet(System.IO.BinaryReader sr);
    public static System.Collections.Generic.Dictionary<System.String, System.Int32> ReadStringIntDictionary(System.IO.BinaryReader sr);
    public static System.String[] ReadStrings(System.IO.BinaryReader sr);
    public static System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> ReadStringVectorDictionary(System.IO.BinaryReader sr);
    public static System.Type ReadType(System.IO.BinaryReader sr);
    public static System.Type[] ReadTypes(System.IO.BinaryReader sr);
    public static Unity.Mathematics.uint2 ReadUInt2(System.IO.BinaryReader sr);
    public static Unity.Mathematics.uint3 ReadUInt3(System.IO.BinaryReader sr);
    public static Unity.Mathematics.uint4 ReadUInt4(System.IO.BinaryReader sr);
    public static System.UInt16[] ReadUShorts(System.IO.BinaryReader sr);
    public static UnityEngine.Vector2 ReadVector2(System.IO.BinaryReader sr);
    public static UnityEngine.Vector2[] ReadVector2s(System.IO.BinaryReader sr);
    public static UnityEngine.Vector3 ReadVector3(System.IO.BinaryReader sr);
    public static UnityEngine.Vector3[] ReadVector3s(System.IO.BinaryReader sr);
    public static UnityEngine.Vector4 ReadVector4(System.IO.BinaryReader sr);
    public static UnityEngine.Vector4[] ReadVector4s(System.IO.BinaryReader sr);
}
```


## Fields

- `private static System.Int32 kMaxAttributes`  

```csharp
private static System.Int32 kMaxAttributes;
```


## Methods

- `public static ReadBounds(System.IO.BinaryReader sr) : UnityEngine.Bounds`  

```csharp
public static UnityEngine.Bounds ReadBounds(System.IO.BinaryReader sr);
```

- `public static ReadColor(System.IO.BinaryReader sr) : UnityEngine.Color`  

```csharp
public static UnityEngine.Color ReadColor(System.IO.BinaryReader sr);
```

- `public static ReadColors(System.IO.BinaryReader sr) : UnityEngine.Color[]`  

```csharp
public static UnityEngine.Color[] ReadColors(System.IO.BinaryReader sr);
```

- `public static ReadFloat2(System.IO.BinaryReader sr) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 ReadFloat2(System.IO.BinaryReader sr);
```

- `public static ReadFloat3(System.IO.BinaryReader sr) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 ReadFloat3(System.IO.BinaryReader sr);
```

- `public static ReadFloat4(System.IO.BinaryReader sr) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 ReadFloat4(System.IO.BinaryReader sr);
```

- `public static ReadGuid(System.IO.BinaryReader sr) : System.Guid`  

```csharp
public static System.Guid ReadGuid(System.IO.BinaryReader sr);
```

- `public static ReadInt2(System.IO.BinaryReader sr) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 ReadInt2(System.IO.BinaryReader sr);
```

- `public static ReadInt3(System.IO.BinaryReader sr) : Unity.Mathematics.int3`  

```csharp
public static Unity.Mathematics.int3 ReadInt3(System.IO.BinaryReader sr);
```

- `public static ReadInt4(System.IO.BinaryReader sr) : Unity.Mathematics.int4`  

```csharp
public static Unity.Mathematics.int4 ReadInt4(System.IO.BinaryReader sr);
```

- `public static ReadInts(System.IO.BinaryReader sr) : System.Int32[]`  

```csharp
public static System.Int32[] ReadInts(System.IO.BinaryReader sr);
```

- `public static ReadMeshAttribute(System.IO.BinaryReader sr) : UnityEngine.Rendering.VertexAttribute`  

```csharp
public static UnityEngine.Rendering.VertexAttribute ReadMeshAttribute(System.IO.BinaryReader sr);
```

- `public static ReadMeshAttributeData(System.IO.BinaryReader sr, UnityEngine.Mesh mesh) : System.Int64`  

```csharp
public static System.Int64 ReadMeshAttributeData(System.IO.BinaryReader sr, UnityEngine.Mesh mesh);
```

- `public static ReadMeshData(System.IO.BinaryReader sr, UnityEngine.Mesh mesh) : System.Int64`  

```csharp
public static System.Int64 ReadMeshData(System.IO.BinaryReader sr, UnityEngine.Mesh mesh);
```

- `public static ReadNull(System.IO.BinaryReader sr) : System.Boolean`  

```csharp
public static System.Boolean ReadNull(System.IO.BinaryReader sr);
```

- `public static ReadNullableString(System.IO.BinaryReader sr) : System.String`  

```csharp
public static System.String ReadNullableString(System.IO.BinaryReader sr);
```

- `public static ReadRect(System.IO.BinaryReader sr) : UnityEngine.Rect`  

```csharp
public static UnityEngine.Rect ReadRect(System.IO.BinaryReader sr);
```

- `public static ReadRectList(System.IO.BinaryReader sr) : System.Collections.Generic.List<UnityEngine.Rect>`  

```csharp
public static System.Collections.Generic.List<UnityEngine.Rect> ReadRectList(System.IO.BinaryReader sr);
```

- `public static ReadStringColorDictionary(System.IO.BinaryReader sr) : System.Collections.Generic.Dictionary<System.String, UnityEngine.Color>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> ReadStringColorDictionary(System.IO.BinaryReader sr);
```

- `public static ReadStringFloatDictionary(System.IO.BinaryReader sr) : System.Collections.Generic.Dictionary<System.String, System.Single>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, System.Single> ReadStringFloatDictionary(System.IO.BinaryReader sr);
```

- `public static ReadStringHashSet(System.IO.BinaryReader sr) : System.Collections.Generic.HashSet<System.String>`  

```csharp
public static System.Collections.Generic.HashSet<System.String> ReadStringHashSet(System.IO.BinaryReader sr);
```

- `public static ReadStringIntDictionary(System.IO.BinaryReader sr) : System.Collections.Generic.Dictionary<System.String, System.Int32>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, System.Int32> ReadStringIntDictionary(System.IO.BinaryReader sr);
```

- `public static ReadStrings(System.IO.BinaryReader sr) : System.String[]`  

```csharp
public static System.String[] ReadStrings(System.IO.BinaryReader sr);
```

- `public static ReadStringVectorDictionary(System.IO.BinaryReader sr) : System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4>`  

```csharp
public static System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> ReadStringVectorDictionary(System.IO.BinaryReader sr);
```

- `public static ReadType(System.IO.BinaryReader sr) : System.Type`  

```csharp
public static System.Type ReadType(System.IO.BinaryReader sr);
```

- `public static ReadTypes(System.IO.BinaryReader sr) : System.Type[]`  

```csharp
public static System.Type[] ReadTypes(System.IO.BinaryReader sr);
```

- `public static ReadUInt2(System.IO.BinaryReader sr) : Unity.Mathematics.uint2`  

```csharp
public static Unity.Mathematics.uint2 ReadUInt2(System.IO.BinaryReader sr);
```

- `public static ReadUInt3(System.IO.BinaryReader sr) : Unity.Mathematics.uint3`  

```csharp
public static Unity.Mathematics.uint3 ReadUInt3(System.IO.BinaryReader sr);
```

- `public static ReadUInt4(System.IO.BinaryReader sr) : Unity.Mathematics.uint4`  

```csharp
public static Unity.Mathematics.uint4 ReadUInt4(System.IO.BinaryReader sr);
```

- `public static ReadUShorts(System.IO.BinaryReader sr) : System.UInt16[]`  

```csharp
public static System.UInt16[] ReadUShorts(System.IO.BinaryReader sr);
```

- `public static ReadVector2(System.IO.BinaryReader sr) : UnityEngine.Vector2`  

```csharp
public static UnityEngine.Vector2 ReadVector2(System.IO.BinaryReader sr);
```

- `public static ReadVector2s(System.IO.BinaryReader sr) : UnityEngine.Vector2[]`  

```csharp
public static UnityEngine.Vector2[] ReadVector2s(System.IO.BinaryReader sr);
```

- `public static ReadVector3(System.IO.BinaryReader sr) : UnityEngine.Vector3`  

```csharp
public static UnityEngine.Vector3 ReadVector3(System.IO.BinaryReader sr);
```

- `public static ReadVector3s(System.IO.BinaryReader sr) : UnityEngine.Vector3[]`  

```csharp
public static UnityEngine.Vector3[] ReadVector3s(System.IO.BinaryReader sr);
```

- `public static ReadVector4(System.IO.BinaryReader sr) : UnityEngine.Vector4`  

```csharp
public static UnityEngine.Vector4 ReadVector4(System.IO.BinaryReader sr);
```

- `public static ReadVector4s(System.IO.BinaryReader sr) : UnityEngine.Vector4[]`  

```csharp
public static UnityEngine.Vector4[] ReadVector4s(System.IO.BinaryReader sr);
```


