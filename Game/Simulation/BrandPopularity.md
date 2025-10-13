# Game.Simulation.BrandPopularitySystem+BrandPopularity

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Simulation.BrandPopularitySystem+BrandPopularity>`  

## Code

```csharp
public sealed struct BrandPopularity : System.IComparable<Game.Simulation.BrandPopularitySystem+BrandPopularity>
{
    public Unity.Entities.Entity m_BrandPrefab;
    public System.Int32 m_Popularity;

    public System.Int32 CompareTo(Game.Simulation.BrandPopularitySystem+BrandPopularity other);
}
```


## Fields

- `public Unity.Entities.Entity m_BrandPrefab`  

```csharp
public Unity.Entities.Entity m_BrandPrefab;
```

- `public System.Int32 m_Popularity`  

```csharp
public System.Int32 m_Popularity;
```


## Methods

- `public CompareTo(Game.Simulation.BrandPopularitySystem+BrandPopularity other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Simulation.BrandPopularitySystem+BrandPopularity other);
```


