# Game.Buildings.RoadConnectionUpdated

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct RoadConnectionUpdated : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Building;
    public Unity.Entities.Entity m_Old;
    public Unity.Entities.Entity m_New;

}
```


## Fields

- `public Unity.Entities.Entity m_Building`  

```csharp
public Unity.Entities.Entity m_Building;
```

- `public Unity.Entities.Entity m_Old`  

```csharp
public Unity.Entities.Entity m_Old;
```

- `public Unity.Entities.Entity m_New`  

```csharp
public Unity.Entities.Entity m_New;
```


