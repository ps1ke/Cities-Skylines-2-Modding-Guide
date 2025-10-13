# Game.Vehicles.GuestVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Vehicles.GuestVehicle>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct GuestVehicle : Unity.Entities.IBufferElementData, System.IEquatable<Game.Vehicles.GuestVehicle>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Vehicle;

    public GuestVehicle(Unity.Entities.Entity vehicle);

    public System.Boolean Equals(Game.Vehicles.GuestVehicle other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Vehicle`  

```csharp
public Unity.Entities.Entity m_Vehicle;
```


## Constructors

- `public GuestVehicle(Unity.Entities.Entity vehicle)`  

```csharp
public GuestVehicle(Unity.Entities.Entity vehicle);
```


## Methods

- `public Equals(Game.Vehicles.GuestVehicle other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Vehicles.GuestVehicle other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


