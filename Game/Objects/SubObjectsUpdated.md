# Game.Objects.SubObjectsUpdated

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct SubObjectsUpdated : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Owner;

    public SubObjectsUpdated(Unity.Entities.Entity owner);

}
```


## Fields

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```


## Constructors

- `public SubObjectsUpdated(Unity.Entities.Entity owner)`  

```csharp
public SubObjectsUpdated(Entity owner)
	{
		m_Owner = owner;
	}
```


