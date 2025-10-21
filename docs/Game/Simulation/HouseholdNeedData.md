# Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData>`  

## Code

```csharp
public sealed struct HouseholdNeedData : Colossal.Collections.IAccumulable<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData>
{
    public System.Int32 m_HouseholdNeed;

    public System.Void Accumulate(Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData other);
}
```


## Fields

- `public System.Int32 m_HouseholdNeed`  

```csharp
public System.Int32 m_HouseholdNeed;
```


## Methods

- `public Accumulate(Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData other) : System.Void`  

```csharp
public System.Void Accumulate(Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData other);
```


