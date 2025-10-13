# Game.Net.SubLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.SubLane>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubLane : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.SubLane>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_SubLane;
    public Game.Pathfind.PathMethod m_PathMethods;

    public SubLane(Unity.Entities.Entity lane, Game.Pathfind.PathMethod pathMethods);

    public System.Boolean Equals(Game.Net.SubLane other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_SubLane`  

```csharp
public Unity.Entities.Entity m_SubLane;
```

- `public Game.Pathfind.PathMethod m_PathMethods`  

```csharp
public Game.Pathfind.PathMethod m_PathMethods;
```


## Constructors

- `public SubLane(Unity.Entities.Entity lane, Game.Pathfind.PathMethod pathMethods)`  

```csharp
public SubLane(Entity lane, PathMethod pathMethods)
	{
		m_SubLane = lane;
		m_PathMethods = pathMethods;
	}
```


## Methods

- `public Equals(Game.Net.SubLane other) : System.Boolean`  

```csharp
public bool Equals(SubLane other)
	{
		return m_SubLane.Equals(other.m_SubLane);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_SubLane.GetHashCode();
	}
```


