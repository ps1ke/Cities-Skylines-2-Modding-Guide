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
public MeshVertex(Unity.Mathematics.float3 vertex);
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshVertex> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```


