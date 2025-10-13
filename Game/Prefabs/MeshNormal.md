# Game.Prefabs.MeshNormal

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MeshNormal : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float3 m_Normal;

    public MeshNormal(Unity.Mathematics.float3 normal);

    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Normal`  

```csharp
public Unity.Mathematics.float3 m_Normal;
```


## Constructors

- `public MeshNormal(Unity.Mathematics.float3 normal)`  

```csharp
public MeshNormal(float3 normal)
	{
		m_Normal = normal;
	}
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public unsafe static void Unpack(NativeSlice<byte> src, NativeArray<MeshNormal> dst, int count, VertexAttributeFormat format, int dimension)
	{
		if (format == VertexAttributeFormat.Float32 && dimension == 3)
		{
			src.SliceConvert<MeshNormal>().CopyTo(dst);
			return;
		}
		switch (format)
		{
		case VertexAttributeFormat.Float16:
			NativeMath.ArrayHalfToFloat((IntPtr)src.GetUnsafeReadOnlyPtr(), count, dimension, (IntPtr)dst.GetUnsafePtr(), 3);
			return;
		case VertexAttributeFormat.SNorm16:
			if (dimension == 2)
			{
				NativeMath.ArrayOctahedralToNormals((IntPtr)src.GetUnsafeReadOnlyPtr(), count, (IntPtr)dst.GetUnsafePtr());
				return;
			}
			break;
		}
		throw new Exception($"Unsupported source normals format/dimension in Unpack {format} {dimension}");
	}
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public unsafe static void Unpack(NativeSlice<byte> src, NativeArray<MeshNormal> dst, int count, VertexAttributeFormat format, int dimension)
	{
		if (format == VertexAttributeFormat.Float32 && dimension == 3)
		{
			src.SliceConvert<MeshNormal>().CopyTo(dst);
			return;
		}
		switch (format)
		{
		case VertexAttributeFormat.Float16:
			NativeMath.ArrayHalfToFloat((IntPtr)src.GetUnsafeReadOnlyPtr(), count, dimension, (IntPtr)dst.GetUnsafePtr(), 3);
			return;
		case VertexAttributeFormat.SNorm16:
			if (dimension == 2)
			{
				NativeMath.ArrayOctahedralToNormals((IntPtr)src.GetUnsafeReadOnlyPtr(), count, (IntPtr)dst.GetUnsafePtr());
				return;
			}
			break;
		}
		throw new Exception($"Unsupported source normals format/dimension in Unpack {format} {dimension}");
	}
```


