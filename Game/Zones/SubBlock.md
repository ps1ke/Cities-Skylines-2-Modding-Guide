# Game.Zones.SubBlock

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Zones.SubBlock>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubBlock : Unity.Entities.IBufferElementData, System.IEquatable<Game.Zones.SubBlock>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_SubBlock;

    public SubBlock(Unity.Entities.Entity block);

    public System.Boolean Equals(Game.Zones.SubBlock other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_SubBlock`  

```csharp
public Unity.Entities.Entity m_SubBlock;
```


## Constructors

- `public SubBlock(Unity.Entities.Entity block)`  

```csharp
public SubBlock(Unity.Entities.Entity block);
```


## Methods

- `public Equals(Game.Zones.SubBlock other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Zones.SubBlock other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


