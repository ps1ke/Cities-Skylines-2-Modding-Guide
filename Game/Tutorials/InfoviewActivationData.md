# Game.Tutorials.InfoviewActivationData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct InfoviewActivationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Infoview;

    public InfoviewActivationData(Unity.Entities.Entity infoview);

}
```


## Fields

- `public Unity.Entities.Entity m_Infoview`  

```csharp
public Unity.Entities.Entity m_Infoview;
```


## Constructors

- `public InfoviewActivationData(Unity.Entities.Entity infoview)`  

```csharp
public InfoviewActivationData(Entity infoview)
	{
		m_Infoview = infoview;
	}
```


