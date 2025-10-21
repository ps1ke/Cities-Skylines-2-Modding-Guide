# Game.Prefabs.EffectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct EffectData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.EntityArchetype m_Archetype;
    public Game.Prefabs.EffectCondition m_Flags;
    public System.Boolean m_OwnerCulling;

}
```


## Fields

- `public Unity.Entities.EntityArchetype m_Archetype`  

```csharp
public Unity.Entities.EntityArchetype m_Archetype;
```

- `public Game.Prefabs.EffectCondition m_Flags`  

```csharp
public Game.Prefabs.EffectCondition m_Flags;
```

- `public System.Boolean m_OwnerCulling`  

```csharp
public System.Boolean m_OwnerCulling;
```


