# Game.Buildings.ConnectedBuilding

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Buildings.ConnectedBuilding>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ConnectedBuilding : Unity.Entities.IBufferElementData, System.IEquatable<Game.Buildings.ConnectedBuilding>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Building;

    public ConnectedBuilding(Unity.Entities.Entity building);

    public System.Boolean Equals(Game.Buildings.ConnectedBuilding other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Building`  

```csharp
public Unity.Entities.Entity m_Building;
```


## Constructors

- `public ConnectedBuilding(Unity.Entities.Entity building)`  

```csharp
public ConnectedBuilding(Unity.Entities.Entity building);
```


## Methods

- `public Equals(Game.Buildings.ConnectedBuilding other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Buildings.ConnectedBuilding other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


