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
public ConnectedFlowEdge(Unity.Entities.Entity edge);
```


## Methods

- `public Equals(Game.Simulation.ConnectedFlowEdge other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Simulation.ConnectedFlowEdge other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


