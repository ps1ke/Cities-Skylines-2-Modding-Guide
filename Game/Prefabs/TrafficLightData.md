# Game.Prefabs.TrafficLightData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TrafficLightData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Prefabs.TrafficLightType m_Type;
    public Colossal.Mathematics.Bounds1 m_ReachOffset;

}
```


## Fields

- `public Game.Prefabs.TrafficLightType m_Type`  

```csharp
public Game.Prefabs.TrafficLightType m_Type;
```

- `public Colossal.Mathematics.Bounds1 m_ReachOffset`  

```csharp
public Colossal.Mathematics.Bounds1 m_ReachOffset;
```


