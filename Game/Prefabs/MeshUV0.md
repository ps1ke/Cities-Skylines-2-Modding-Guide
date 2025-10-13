# Game.Prefabs.MeshUV0

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MeshUV0 : Unity.Entities.IBufferElementData
{
    public Unity.Mathematics.float2 m_Uv;

    public MeshUV0(Unity.Mathematics.float2 uv);

    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshUV0> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
    public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshUV0> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
}
```


## Fields

- `public Unity.Mathematics.float2 m_Uv`  

```csharp
public Unity.Mathematics.float2 m_Uv;
```


## Constructors

- `public MeshUV0(Unity.Mathematics.float2 uv)`  

```csharp
public MeshUV0(Unity.Mathematics.float2 uv);
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshUV0> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshUV0> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshUV0> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshUV0> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```


