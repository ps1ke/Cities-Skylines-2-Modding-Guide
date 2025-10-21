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
public MeshIndex(System.Int32 index);
```


## Methods

- `public static Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format);
```

- `public static Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format, System.Int32 vertexOffset) : System.Void`  

```csharp
public static System.Void Unpack(Unity.Collections.NativeArray<System.Byte> src, Unity.Collections.NativeArray<Game.Prefabs.MeshIndex> dst, System.Int32 count, UnityEngine.Rendering.IndexFormat format, System.Int32 vertexOffset);
```


