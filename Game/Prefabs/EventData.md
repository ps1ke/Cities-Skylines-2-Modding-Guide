# Game.Prefabs.EventData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct EventData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.EntityArchetype m_Archetype;
    public System.Int32 m_ConcurrentLimit;

}
```


## Fields

- `public Unity.Entities.EntityArchetype m_Archetype`  

```csharp
public Unity.Entities.EntityArchetype m_Archetype;
```

- `public System.Int32 m_ConcurrentLimit`  

```csharp
public System.Int32 m_ConcurrentLimit;
```


