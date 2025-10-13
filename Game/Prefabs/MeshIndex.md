# Game.Prefabs.MeshIndex

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MeshIndex : Unity.Entities.IBufferElementData
{
    public System.Int32 m_Index;

    public MeshIndex(System.Int32 index);

    public static System.Void Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format);
    public static System.Void Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format, System.Int32 vertexOffset);
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```


## Constructors

- `public MeshIndex(System.Int32 index)`  

```csharp
public MeshIndex(int index)
	{
		m_Index = index;
	}
```


## Methods

- `public static Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format) : System.Void`  

```csharp
public static void Unpack(NativeArray<byte> src, NativeArray<MeshIndex> dst, int count, IndexFormat format, int vertexOffset)
	{
		if (format == IndexFormat.UInt32)
		{
			NativeArray<int> nativeArray = src.Reinterpret<int>(1);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				dst[i] = new MeshIndex(nativeArray[i] + vertexOffset);
			}
		}
		else
		{
			NativeArray<ushort> nativeArray2 = src.Reinterpret<ushort>(1);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				dst[j] = new MeshIndex(nativeArray2[j] + vertexOffset);
			}
		}
	}
```

- `public static Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format, System.Int32 vertexOffset) : System.Void`  

```csharp
public static void Unpack(NativeArray<byte> src, NativeArray<MeshIndex> dst, int count, IndexFormat format, int vertexOffset)
	{
		if (format == IndexFormat.UInt32)
		{
			NativeArray<int> nativeArray = src.Reinterpret<int>(1);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				dst[i] = new MeshIndex(nativeArray[i] + vertexOffset);
			}
		}
		else
		{
			NativeArray<ushort> nativeArray2 = src.Reinterpret<ushort>(1);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				dst[j] = new MeshIndex(nativeArray2[j] + vertexOffset);
			}
		}
	}
```


