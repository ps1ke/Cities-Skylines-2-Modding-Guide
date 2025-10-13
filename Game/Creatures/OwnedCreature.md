# Game.Creatures.OwnedCreature

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Creatures.OwnedCreature>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct OwnedCreature : Unity.Entities.IBufferElementData, System.IEquatable<Game.Creatures.OwnedCreature>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Creature;

    public OwnedCreature(Unity.Entities.Entity creature);

    public System.Boolean Equals(Game.Creatures.OwnedCreature other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Creature`  

```csharp
public Unity.Entities.Entity m_Creature;
```


## Constructors

- `public OwnedCreature(Unity.Entities.Entity creature)`  

```csharp
public OwnedCreature(Unity.Entities.Entity creature);
```


## Methods

- `public Equals(Game.Creatures.OwnedCreature other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Creatures.OwnedCreature other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


