# Game.Tutorials.TutorialRef

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`  

## Code

```csharp
public sealed struct TutorialRef : Unity.Entities.IBufferElementData
{
    public Unity.Entities.Entity m_Tutorial;

    public TutorialRef(Unity.Entities.Entity tutorial);

}
```


## Fields

- `public Unity.Entities.Entity m_Tutorial`  

```csharp
public Unity.Entities.Entity m_Tutorial;
```


## Constructors

- `public TutorialRef(Unity.Entities.Entity tutorial)`  

```csharp
public TutorialRef(Entity tutorial)
	{
		m_Tutorial = tutorial;
	}
```


