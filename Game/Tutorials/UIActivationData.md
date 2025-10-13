# Game.Tutorials.UIActivationData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct UIActivationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public System.Boolean m_CanDeactivate;

    public UIActivationData(System.Boolean canDeactivate);

}
```


## Fields

- `public System.Boolean m_CanDeactivate`  

```csharp
public System.Boolean m_CanDeactivate;
```


## Constructors

- `public UIActivationData(System.Boolean canDeactivate)`  

```csharp
public UIActivationData(bool canDeactivate)
	{
		m_CanDeactivate = canDeactivate;
	}
```


