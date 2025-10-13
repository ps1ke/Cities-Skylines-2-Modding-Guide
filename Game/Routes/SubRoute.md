# Game.Routes.SubRoute

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Routes.SubRoute>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubRoute : Unity.Entities.IBufferElementData, System.IEquatable<Game.Routes.SubRoute>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Route;

    public SubRoute(Unity.Entities.Entity route);

    public System.Boolean Equals(Game.Routes.SubRoute other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Route`  

```csharp
public Unity.Entities.Entity m_Route;
```


## Constructors

- `public SubRoute(Unity.Entities.Entity route)`  

```csharp
public SubRoute(Entity route)
	{
		m_Route = route;
	}
```


## Methods

- `public Equals(Game.Routes.SubRoute other) : System.Boolean`  

```csharp
public bool Equals(SubRoute other)
	{
		return m_Route.Equals(other.m_Route);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Route.GetHashCode();
	}
```


