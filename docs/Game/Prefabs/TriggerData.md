# Game.Prefabs.TriggerData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct TriggerData : Unity.Entities.IBufferElementData
{
    public Game.Triggers.TriggerType m_TriggerType;
    public Game.Triggers.TargetType m_TargetTypes;
    public Unity.Entities.Entity m_TriggerPrefab;

}
```


## Fields

- `public Game.Triggers.TriggerType m_TriggerType`  

```csharp
public Game.Triggers.TriggerType m_TriggerType;
```

- `public Game.Triggers.TargetType m_TargetTypes`  

```csharp
public Game.Triggers.TargetType m_TargetTypes;
```

- `public Unity.Entities.Entity m_TriggerPrefab`  

```csharp
public Unity.Entities.Entity m_TriggerPrefab;
```


