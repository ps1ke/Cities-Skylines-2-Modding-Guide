# Game.Net.SubNet

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.SubNet>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubNet : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.SubNet>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_SubNet;

    public SubNet(Unity.Entities.Entity subNet);

    public System.Boolean Equals(Game.Net.SubNet other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_SubNet`  

```csharp
public Unity.Entities.Entity m_SubNet;
```


## Constructors

- `public SubNet(Unity.Entities.Entity subNet)`  

```csharp
public SubNet(Unity.Entities.Entity subNet);
```


## Methods

- `public Equals(Game.Net.SubNet other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Net.SubNet other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


