# Game.Prefabs.BatchGroup

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct BatchGroup : Unity.Entities.IBufferElementData
{
    public System.Int32 m_GroupIndex;
    public System.Int32 m_MergeIndex;
    public Game.Prefabs.MeshLayer m_Layer;
    public Game.Prefabs.MeshType m_Type;
    public System.UInt16 m_Partition;

}
```


## Fields

- `public System.Int32 m_GroupIndex`  

```csharp
public System.Int32 m_GroupIndex;
```

- `public System.Int32 m_MergeIndex`  

```csharp
public System.Int32 m_MergeIndex;
```

- `public Game.Prefabs.MeshLayer m_Layer`  

```csharp
public Game.Prefabs.MeshLayer m_Layer;
```

- `public Game.Prefabs.MeshType m_Type`  

```csharp
public Game.Prefabs.MeshType m_Type;
```

- `public System.UInt16 m_Partition`  

```csharp
public System.UInt16 m_Partition;
```


