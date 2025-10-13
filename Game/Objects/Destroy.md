# Game.Objects.Destroy

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct Destroy : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_Object;
    public Unity.Entities.Entity m_Event;

    public Destroy(Unity.Entities.Entity _object, Unity.Entities.Entity _event);

}
```


## Fields

- `public Unity.Entities.Entity m_Object`  

```csharp
public Unity.Entities.Entity m_Object;
```

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```


## Constructors

- `public Destroy(Unity.Entities.Entity _object, Unity.Entities.Entity _event)`  

```csharp
public Destroy(Entity _object, Entity _event)
	{
		m_Object = _object;
		m_Event = _event;
	}
```


