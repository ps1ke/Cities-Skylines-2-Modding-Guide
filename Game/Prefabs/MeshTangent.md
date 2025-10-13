# Game.Prefabs.MeshTangent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MeshTangent : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float4 m_Tangent;

    public MeshTangent(Unity.Mathematics.float4 tangent);

    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
}
```


## Fields

- `public Unity.Mathematics.float4 m_Tangent`  

```csharp
public Unity.Mathematics.float4 m_Tangent;
```


## Constructors

- `public MeshTangent(Unity.Mathematics.float4 tangent)`  

```csharp
public MeshTangent(float4 tangent)
	{
		m_Tangent = tangent;
	}
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public unsafe static void Unpack(NativeSlice<byte> src, NativeArray<MeshTangent> dst, int count, VertexAttributeFormat format, int dimension)
	{
		if (format == VertexAttributeFormat.Float32 && dimension == 4)
		{
			src.SliceConvert<MeshTangent>().CopyTo(dst);
			return;
		}
		switch (format)
		{
		case VertexAttributeFormat.Float16:
			NativeMath.ArrayHalfToFloat((IntPtr)src.GetUnsafeReadOnlyPtr(), count, dimension, (IntPtr)dst.GetUnsafePtr(), 4);
			return;
		case VertexAttributeFormat.Float32:
			if (dimension == 1)
			{
				NativeMath.ArrayOctahedralToTangents((IntPtr)src.GetUnsafeReadOnlyPtr(), count, (IntPtr)dst.GetUnsafePtr());
				return;
			}
			break;
		}
		throw new Exception($"Unsupported source tangents format/dimension in Unpack {format} {dimension}");
	}
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public unsafe static void Unpack(NativeSlice<byte> src, NativeArray<MeshTangent> dst, int count, VertexAttributeFormat format, int dimension)
	{
		if (format == VertexAttributeFormat.Float32 && dimension == 4)
		{
			src.SliceConvert<MeshTangent>().CopyTo(dst);
			return;
		}
		switch (format)
		{
		case VertexAttributeFormat.Float16:
			NativeMath.ArrayHalfToFloat((IntPtr)src.GetUnsafeReadOnlyPtr(), count, dimension, (IntPtr)dst.GetUnsafePtr(), 4);
			return;
		case VertexAttributeFormat.Float32:
			if (dimension == 1)
			{
				NativeMath.ArrayOctahedralToTangents((IntPtr)src.GetUnsafeReadOnlyPtr(), count, (IntPtr)dst.GetUnsafePtr());
				return;
			}
			break;
		}
		throw new Exception($"Unsupported source tangents format/dimension in Unpack {format} {dimension}");
	}
```


