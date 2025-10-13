# Game.Prefabs.WildlifeData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct WildlifeData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Colossal.Mathematics.Bounds1 m_TripLength;
    public Colossal.Mathematics.Bounds1 m_IdleTime;
    public Unity.Mathematics.int2 m_GroupMemberCount;

}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_TripLength`  

```csharp
public Colossal.Mathematics.Bounds1 m_TripLength;
```

- `public Colossal.Mathematics.Bounds1 m_IdleTime`  

```csharp
public Colossal.Mathematics.Bounds1 m_IdleTime;
```

- `public Unity.Mathematics.int2 m_GroupMemberCount`  

```csharp
public Unity.Mathematics.int2 m_GroupMemberCount;
```


