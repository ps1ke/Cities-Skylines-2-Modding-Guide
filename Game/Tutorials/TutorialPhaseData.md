# Game.Tutorials.TutorialPhaseData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TutorialPhaseData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Tutorials.TutorialPhaseType m_Type;
    public System.Single m_OverrideCompletionDelay;

}
```


## Fields

- `public Game.Tutorials.TutorialPhaseType m_Type`  

```csharp
public Game.Tutorials.TutorialPhaseType m_Type;
```

- `public System.Single m_OverrideCompletionDelay`  

```csharp
public System.Single m_OverrideCompletionDelay;
```


