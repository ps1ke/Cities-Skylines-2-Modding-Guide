# Game.Prefabs.SubMeshGroup

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubMeshGroup : Unity.Entities.IBufferElementData
{
    public System.Int32 m_SubGroupCount;
    public Unity.Mathematics.int2 m_SubMeshRange;
    public Game.Prefabs.MeshGroupFlags m_Flags;

}
```


## Fields

- `public System.Int32 m_SubGroupCount`  

```csharp
public System.Int32 m_SubGroupCount;
```

- `public Unity.Mathematics.int2 m_SubMeshRange`  

```csharp
public Unity.Mathematics.int2 m_SubMeshRange;
```

- `public Game.Prefabs.MeshGroupFlags m_Flags`  

```csharp
public Game.Prefabs.MeshGroupFlags m_Flags;
```


