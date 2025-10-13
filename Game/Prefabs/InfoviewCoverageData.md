# Game.Prefabs.InfoviewCoverageData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct InfoviewCoverageData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Net.CoverageService m_Service;
    public Colossal.Mathematics.Bounds1 m_Range;

}
```


## Fields

- `public Game.Net.CoverageService m_Service`  

```csharp
public Game.Net.CoverageService m_Service;
```

- `public Colossal.Mathematics.Bounds1 m_Range`  

```csharp
public Colossal.Mathematics.Bounds1 m_Range;
```


