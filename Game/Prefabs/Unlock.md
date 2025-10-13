# Game.Prefabs.Unlock

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Unlock : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Prefab;

    public Unlock(Unity.Entities.Entity prefab);

}
```


## Fields

- `public Unity.Entities.Entity m_Prefab`  

```csharp
public Unity.Entities.Entity m_Prefab;
```


## Constructors

- `public Unlock(Unity.Entities.Entity prefab)`  

```csharp
public Unlock(Entity prefab)
	{
		m_Prefab = prefab;
	}
```


