# Game.Vehicles.OwnedVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Vehicles.OwnedVehicle>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct OwnedVehicle : Unity.Entities.IBufferElementData, System.IEquatable<Game.Vehicles.OwnedVehicle>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Vehicle;

    public OwnedVehicle(Unity.Entities.Entity vehicle);

    public System.Boolean Equals(Game.Vehicles.OwnedVehicle other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Vehicle`  

```csharp
public Unity.Entities.Entity m_Vehicle;
```


## Constructors

- `public OwnedVehicle(Unity.Entities.Entity vehicle)`  

```csharp
public OwnedVehicle(Unity.Entities.Entity vehicle);
```


## Methods

- `public Equals(Game.Vehicles.OwnedVehicle other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Vehicles.OwnedVehicle other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


