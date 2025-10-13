# Game.Buildings.RentersUpdated

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct RentersUpdated : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Property;

    public RentersUpdated(Unity.Entities.Entity property);

}
```


## Fields

- `public Unity.Entities.Entity m_Property`  

```csharp
public Unity.Entities.Entity m_Property;
```


## Constructors

- `public RentersUpdated(Unity.Entities.Entity property)`  

```csharp
public RentersUpdated(Entity property)
	{
		m_Property = property;
	}
```


