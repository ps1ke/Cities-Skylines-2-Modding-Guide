# Game.Prefabs.ProcessingRequirementData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ProcessingRequirementData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Economy.Resource m_ResourceType;
    public System.Int32 m_MinimumProducedAmount;

}
```


## Fields

- `public Game.Economy.Resource m_ResourceType`  

```csharp
public Game.Economy.Resource m_ResourceType;
```

- `public System.Int32 m_MinimumProducedAmount`  

```csharp
public System.Int32 m_MinimumProducedAmount;
```


