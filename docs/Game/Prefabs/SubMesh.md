# Game.Prefabs.SubMesh

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Fields

- `public Unity.Entities.Entity m_SubMesh`  
- `public Unity.Mathematics.float3 m_Position`  
- `public Unity.Mathematics.quaternion m_Rotation`  
- `public Game.Prefabs.SubMeshFlags m_Flags`  
- `public System.UInt16 m_RandomSeed`  

## Constructors

- `public SubMesh(Unity.Entities.Entity mesh, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed)`  
- `public SubMesh(Unity.Entities.Entity mesh, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.SubMeshFlags flags, System.UInt16 randomSeed)`  

