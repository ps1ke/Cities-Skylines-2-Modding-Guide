# Game.Prefabs.LifePathEventData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct LifePathEventData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.EntityArchetype m_ChirpArchetype;
    public Game.Prefabs.LifePathEventType m_EventType;
    public System.Boolean m_IsChirp;

}
```


## Fields

- `public Unity.Entities.EntityArchetype m_ChirpArchetype`  

```csharp
public Unity.Entities.EntityArchetype m_ChirpArchetype;
```

- `public Game.Prefabs.LifePathEventType m_EventType`  

```csharp
public Game.Prefabs.LifePathEventType m_EventType;
```

- `public System.Boolean m_IsChirp`  

```csharp
public System.Boolean m_IsChirp;
```


