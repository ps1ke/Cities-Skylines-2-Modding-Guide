# Game.Routes.RouteVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Routes.RouteVehicle>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct RouteVehicle : Unity.Entities.IBufferElementData, System.IEquatable<Game.Routes.RouteVehicle>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Vehicle;

    public RouteVehicle(Unity.Entities.Entity vehicle);

    public System.Boolean Equals(Game.Routes.RouteVehicle other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Vehicle`  

```csharp
public Unity.Entities.Entity m_Vehicle;
```


## Constructors

- `public RouteVehicle(Unity.Entities.Entity vehicle)`  

```csharp
public RouteVehicle(Unity.Entities.Entity vehicle);
```


## Methods

- `public Equals(Game.Routes.RouteVehicle other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Routes.RouteVehicle other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


