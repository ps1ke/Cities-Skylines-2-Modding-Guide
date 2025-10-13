# Game.Prefabs.CalendarEventData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct CalendarEventData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public Game.Prefabs.CalendarEventMonths m_AllowedMonths;
    public Game.Prefabs.CalendarEventTimes m_AllowedTimes;
    public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
    public Colossal.Mathematics.Bounds1 m_AffectedProbability;
    public System.Int32 m_Duration;

}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomTargetType;
```

- `public Game.Prefabs.CalendarEventMonths m_AllowedMonths`  

```csharp
public Game.Prefabs.CalendarEventMonths m_AllowedMonths;
```

- `public Game.Prefabs.CalendarEventTimes m_AllowedTimes`  

```csharp
public Game.Prefabs.CalendarEventTimes m_AllowedTimes;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_AffectedProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_AffectedProbability;
```

- `public System.Int32 m_Duration`  

```csharp
public System.Int32 m_Duration;
```


