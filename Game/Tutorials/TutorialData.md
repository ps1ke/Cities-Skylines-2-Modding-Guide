# Game.Tutorials.TutorialData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct TutorialData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Int32 m_Priority;

    public TutorialData(System.Int32 priority);

}
```


## Fields

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```


## Constructors

- `public TutorialData(System.Int32 priority)`  

```csharp
public TutorialData(int priority)
	{
		m_Priority = priority;
	}
```


