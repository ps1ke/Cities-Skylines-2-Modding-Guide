# Game.Prefabs.SubMesh

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubMesh : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_SubMesh;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Prefabs.SubMeshFlags m_Flags;
    public System.UInt16 m_RandomSeed;

    public SubMesh(Unity.Entities.Entity mesh, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed);
    public SubMesh(Unity.Entities.Entity mesh, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed);

}
```


## Fields

- `public Unity.Entities.Entity m_SubMesh`  

```csharp
public Unity.Entities.Entity m_SubMesh;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Prefabs.SubMeshFlags m_Flags`  

```csharp
public Game.Prefabs.SubMeshFlags m_Flags;
```

- `public System.UInt16 m_RandomSeed`  

```csharp
public System.UInt16 m_RandomSeed;
```


## Constructors

- `public SubMesh(Unity.Entities.Entity mesh, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed)`  

```csharp
public SubMesh(Unity.Entities.Entity mesh, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed);
```

- `public SubMesh(Unity.Entities.Entity mesh, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed)`  

```csharp
public SubMesh(Unity.Entities.Entity mesh, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed);
```


