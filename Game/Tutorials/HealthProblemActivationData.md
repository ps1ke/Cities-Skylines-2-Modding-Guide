# Game.Tutorials.HealthProblemActivationData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct HealthProblemActivationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Citizens.HealthProblemFlags m_Require;
    public System.Int32 m_RequiredCount;

}
```


## Fields

- `public Game.Citizens.HealthProblemFlags m_Require`  

```csharp
public Game.Citizens.HealthProblemFlags m_Require;
```

- `public System.Int32 m_RequiredCount`  

```csharp
public System.Int32 m_RequiredCount;
```


