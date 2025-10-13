# Game.Prefabs.MeshVertex

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MeshVertex : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float3 m_Vertex;

    public MeshVertex(Unity.Mathematics.float3 vertex);

    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Vertex`  

```csharp
public Unity.Mathematics.float3 m_Vertex;
```


## Constructors

- `public MeshVertex(Unity.Mathematics.float3 vertex)`  

```csharp
public MeshVertex(float3 vertex)
	{
		m_Vertex = vertex;
	}
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public unsafe static void Unpack(NativeSlice<byte> src, NativeArray<MeshVertex> dst, int count, VertexAttributeFormat format, int dimension)
	{
		if (format == VertexAttributeFormat.Float32 && dimension == 3)
		{
			src.SliceConvert<MeshVertex>().CopyTo(dst);
			return;
		}
		if (format == VertexAttributeFormat.Float16)
		{
			NativeMath.ArrayHalfToFloat((IntPtr)src.GetUnsafeReadOnlyPtr(), count, dimension, (IntPtr)dst.GetUnsafePtr(), 3);
			return;
		}
		throw new Exception($"Unsupported source position format/dimension in Unpack {format} {dimension}");
	}
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public unsafe static void Unpack(NativeSlice<byte> src, NativeArray<MeshVertex> dst, int count, VertexAttributeFormat format, int dimension)
	{
		if (format == VertexAttributeFormat.Float32 && dimension == 3)
		{
			src.SliceConvert<MeshVertex>().CopyTo(dst);
			return;
		}
		if (format == VertexAttributeFormat.Float16)
		{
			NativeMath.ArrayHalfToFloat((IntPtr)src.GetUnsafeReadOnlyPtr(), count, dimension, (IntPtr)dst.GetUnsafePtr(), 3);
			return;
		}
		throw new Exception($"Unsupported source position format/dimension in Unpack {format} {dimension}");
	}
```


