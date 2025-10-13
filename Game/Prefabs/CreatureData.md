# Game.Prefabs.CreatureData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct CreatureData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.ActivityMask m_SupportedActivities;
    public Game.Prefabs.GenderMask m_Gender;

}
```


## Fields

- `public Game.Prefabs.ActivityMask m_SupportedActivities`  

```csharp
public Game.Prefabs.ActivityMask m_SupportedActivities;
```

- `public Game.Prefabs.GenderMask m_Gender`  

```csharp
public Game.Prefabs.GenderMask m_Gender;
```


