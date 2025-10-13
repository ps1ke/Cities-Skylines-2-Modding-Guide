# Game.Prefabs.ZoneBlockData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct ZoneBlockData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.EntityArchetype m_Archetype;
    public Game.Prefabs.MeshLayer m_AvailableLayers;
    public System.UInt16 m_AvailablePartitions;

}
```


## Fields

- `public Unity.Entities.EntityArchetype m_Archetype`  

```csharp
public Unity.Entities.EntityArchetype m_Archetype;
```

- `public Game.Prefabs.MeshLayer m_AvailableLayers`  

```csharp
public Game.Prefabs.MeshLayer m_AvailableLayers;
```

- `public System.UInt16 m_AvailablePartitions`  

```csharp
public System.UInt16 m_AvailablePartitions;
```


