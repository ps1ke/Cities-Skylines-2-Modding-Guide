# Game.Prefabs.RadioEventData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct RadioEventData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.EntityArchetype m_Archetype;
    public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
    public System.Int32 m_EmergencyFrameDelay;

}
```


## Fields

- `public Unity.Entities.EntityArchetype m_Archetype`  

```csharp
public Unity.Entities.EntityArchetype m_Archetype;
```

- `public Game.Audio.Radio.Radio+SegmentType m_SegmentType`  

```csharp
public Game.Audio.Radio.Radio+SegmentType m_SegmentType;
```

- `public System.Int32 m_EmergencyFrameDelay`  

```csharp
public System.Int32 m_EmergencyFrameDelay;
```


