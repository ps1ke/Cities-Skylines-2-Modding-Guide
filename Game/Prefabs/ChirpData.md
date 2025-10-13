# Game.Prefabs.ChirpData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ChirpData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.EntityArchetype m_Archetype;
    public Game.Prefabs.ChirpDataFlags m_Flags;
    public Unity.Entities.Entity m_ChirperAccount;

}
```


## Fields

- `public Unity.Entities.EntityArchetype m_Archetype`  

```csharp
public Unity.Entities.EntityArchetype m_Archetype;
```

- `public Game.Prefabs.ChirpDataFlags m_Flags`  

```csharp
public Game.Prefabs.ChirpDataFlags m_Flags;
```

- `public Unity.Entities.Entity m_ChirperAccount`  

```csharp
public Unity.Entities.Entity m_ChirperAccount;
```


