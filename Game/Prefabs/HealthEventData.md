# Game.Prefabs.HealthEventData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct HealthEventData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.EventTargetType m_RandomTargetType;
    public Game.Prefabs.HealthEventType m_HealthEventType;
    public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
    public Colossal.Mathematics.Bounds1 m_TransportProbability;
    public System.Boolean m_RequireTracking;

}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomTargetType;
```

- `public Game.Prefabs.HealthEventType m_HealthEventType`  

```csharp
public Game.Prefabs.HealthEventType m_HealthEventType;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_TransportProbability`  

```csharp
public Colossal.Mathematics.Bounds1 m_TransportProbability;
```

- `public System.Boolean m_RequireTracking`  

```csharp
public System.Boolean m_RequireTracking;
```


