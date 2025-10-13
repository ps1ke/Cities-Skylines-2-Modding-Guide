# Game.Routes.RouteSearchItem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Routes.RouteSearchItem>`  

## Code

```csharp
public sealed struct RouteSearchItem : System.IEquatable<Game.Routes.RouteSearchItem>
{
    public Unity.Entities.Entity m_Entity;
    public System.Int32 m_Element;

    public RouteSearchItem(Unity.Entities.Entity entity, System.Int32 element);

    public System.Boolean Equals(Game.Routes.RouteSearchItem other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public System.Int32 m_Element`  

```csharp
public System.Int32 m_Element;
```


## Constructors

- `public RouteSearchItem(Unity.Entities.Entity entity, System.Int32 element)`  

```csharp
public RouteSearchItem(Entity entity, int element)
	{
		m_Entity = entity;
		m_Element = element;
	}
```


## Methods

- `public Equals(Game.Routes.RouteSearchItem other) : System.Boolean`  

```csharp
public bool Equals(RouteSearchItem other)
	{
		return m_Entity.Equals(other.m_Entity) & m_Element.Equals(other.m_Element);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (17 * 31 + m_Entity.GetHashCode()) * 31 + m_Element.GetHashCode();
	}
```


