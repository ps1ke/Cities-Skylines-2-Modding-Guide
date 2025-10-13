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
public MeshNormal(Unity.Mathematics.float3 normal);
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshNormal> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```


