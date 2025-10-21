# Game.Net.ConnectedNode

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.ConnectedNode>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ConnectedNode : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.ConnectedNode>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Node;
    public System.Single m_CurvePosition;

    public ConnectedNode(Unity.Entities.Entity node, System.Single curvePosition);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Net.ConnectedNode other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Node`  

```csharp
public Unity.Entities.Entity m_Node;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```


## Constructors

- `public ConnectedNode(Unity.Entities.Entity node, System.Single curvePosition)`  

```csharp
public ConnectedNode(Unity.Entities.Entity node, System.Single curvePosition);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Net.ConnectedNode other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Net.ConnectedNode other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


