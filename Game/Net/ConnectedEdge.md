# Game.Net.ConnectedEdge

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.ConnectedEdge>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ConnectedEdge : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.ConnectedEdge>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Edge;

    public ConnectedEdge(Unity.Entities.Entity edge);

    public System.Boolean Equals(Game.Net.ConnectedEdge other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```


## Constructors

- `public ConnectedEdge(Unity.Entities.Entity edge)`  

```csharp
public ConnectedEdge(Unity.Entities.Entity edge);
```


## Methods

- `public Equals(Game.Net.ConnectedEdge other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Net.ConnectedEdge other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


