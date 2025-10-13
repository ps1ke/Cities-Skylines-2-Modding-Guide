# Game.Simulation.ConnectedFlowEdge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`, `System.IEquatable<Game.Simulation.ConnectedFlowEdge>`  

## Code

```csharp
public sealed struct ConnectedFlowEdge : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable, System.IEquatable<Game.Simulation.ConnectedFlowEdge>
{
    public Unity.Entities.Entity m_Edge;

    public ConnectedFlowEdge(Unity.Entities.Entity edge);

    public System.Boolean Equals(Game.Simulation.ConnectedFlowEdge other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```


## Constructors

- `public ConnectedFlowEdge(Unity.Entities.Entity edge)`  

```csharp
public ConnectedFlowEdge(Entity edge)
	{
		m_Edge = edge;
	}
```


## Methods

- `public Equals(Game.Simulation.ConnectedFlowEdge other) : System.Boolean`  

```csharp
public bool Equals(ConnectedFlowEdge other)
	{
		return m_Edge.Equals(other.m_Edge);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Edge.GetHashCode();
	}
```


