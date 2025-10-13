# Game.Prefabs.LeisureParametersData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct LeisureParametersData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_TravelingPrefab;
    public Unity.Entities.Entity m_AttractionPrefab;
    public Unity.Entities.Entity m_SightseeingPrefab;
    public System.Int32 m_LeisureRandomFactor;
    public System.Int32 m_TouristLodgingConsumePerDay;
    public System.Int32 m_TouristServiceConsumePerDay;

    public Unity.Entities.Entity GetPrefab(Game.Agents.LeisureType type);
}
```


## Fields

- `public Unity.Entities.Entity m_TravelingPrefab`  

```csharp
public Unity.Entities.Entity m_TravelingPrefab;
```

- `public Unity.Entities.Entity m_AttractionPrefab`  

```csharp
public Unity.Entities.Entity m_AttractionPrefab;
```

- `public Unity.Entities.Entity m_SightseeingPrefab`  

```csharp
public Unity.Entities.Entity m_SightseeingPrefab;
```

- `public System.Int32 m_LeisureRandomFactor`  

```csharp
public System.Int32 m_LeisureRandomFactor;
```

- `public System.Int32 m_TouristLodgingConsumePerDay`  

```csharp
public System.Int32 m_TouristLodgingConsumePerDay;
```

- `public System.Int32 m_TouristServiceConsumePerDay`  

```csharp
public System.Int32 m_TouristServiceConsumePerDay;
```


## Methods

- `public GetPrefab(Game.Agents.LeisureType type) : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity GetPrefab(Game.Agents.LeisureType type);
```


