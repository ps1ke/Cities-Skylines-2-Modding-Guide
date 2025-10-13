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
public MeshTangent(Unity.Mathematics.float4 tangent);
```


## Methods

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```

- `public static Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeSlice<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshTangent> dst, System.Int32 count, UnityEngine.Rendering.VertexAttributeFormat format, System.Int32 dimension);
```


