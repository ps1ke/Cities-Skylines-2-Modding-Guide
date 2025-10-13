# Game.Prefabs.WaterLevelChangeData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct WaterLevelChangeData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.WaterLevelTargetType m_TargetType;
    public Game.Prefabs.WaterLevelChangeType m_ChangeType;
    public System.Single m_EscalationDelay;
    public Game.Events.DangerFlags m_DangerFlags;
    public System.Single m_DangerLevel;

}
```


## Fields

- `public Game.Prefabs.WaterLevelTargetType m_TargetType`  

```csharp
public Game.Prefabs.WaterLevelTargetType m_TargetType;
```

- `public Game.Prefabs.WaterLevelChangeType m_ChangeType`  

```csharp
public Game.Prefabs.WaterLevelChangeType m_ChangeType;
```

- `public System.Single m_EscalationDelay`  

```csharp
public System.Single m_EscalationDelay;
```

- `public Game.Events.DangerFlags m_DangerFlags`  

```csharp
public Game.Events.DangerFlags m_DangerFlags;
```

- `public System.Single m_DangerLevel`  

```csharp
public System.Single m_DangerLevel;
```


