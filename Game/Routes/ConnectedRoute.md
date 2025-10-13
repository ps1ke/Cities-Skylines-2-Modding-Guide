# Game.Routes.ConnectedRoute

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Routes.ConnectedRoute>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ConnectedRoute : Unity.Entities.IBufferElementData, System.IEquatable<Game.Routes.ConnectedRoute>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Waypoint;

    public ConnectedRoute(Unity.Entities.Entity waypoint);

    public System.Boolean Equals(Game.Routes.ConnectedRoute other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Waypoint`  

```csharp
public Unity.Entities.Entity m_Waypoint;
```


## Constructors

- `public ConnectedRoute(Unity.Entities.Entity waypoint)`  

```csharp
public ConnectedRoute(Entity waypoint)
	{
		m_Waypoint = waypoint;
	}
```


## Methods

- `public Equals(Game.Routes.ConnectedRoute other) : System.Boolean`  

```csharp
public bool Equals(ConnectedRoute other)
	{
		return m_Waypoint.Equals(other.m_Waypoint);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Waypoint.GetHashCode();
	}
```


