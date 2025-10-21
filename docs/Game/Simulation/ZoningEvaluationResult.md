# Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult>`  

## Code

```csharp
public sealed struct ZoningEvaluationResult : System.IComparable<Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult>
{
    public Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor m_Factor;
    public System.Single m_Score;

    public System.Int32 CompareTo(Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult other);
}
```


## Fields

- `public Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor m_Factor`  

```csharp
public Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationFactor m_Factor;
```

- `public System.Single m_Score`  

```csharp
public System.Single m_Score;
```


## Methods

- `public CompareTo(Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Simulation.ZoneEvaluationUtils+ZoningEvaluationResult other);
```


