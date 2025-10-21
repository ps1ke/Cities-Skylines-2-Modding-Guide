# Game.Prefabs.TrafficAccidentData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TrafficAccidentData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.EventTargetType m_RandomSiteType;
    public Game.Prefabs.EventTargetType m_SubjectType;
    public Game.Prefabs.TrafficAccidentType m_AccidentType;
    public System.Single m_OccurenceProbability;

}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomSiteType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomSiteType;
```

- `public Game.Prefabs.EventTargetType m_SubjectType`  

```csharp
public Game.Prefabs.EventTargetType m_SubjectType;
```

- `public Game.Prefabs.TrafficAccidentType m_AccidentType`  

```csharp
public Game.Prefabs.TrafficAccidentType m_AccidentType;
```

- `public System.Single m_OccurenceProbability`  

```csharp
public System.Single m_OccurenceProbability;
```


