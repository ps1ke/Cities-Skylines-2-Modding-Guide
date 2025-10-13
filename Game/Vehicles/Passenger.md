# Game.Vehicles.Passenger

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Vehicles.Passenger>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Passenger : Unity.Entities.IBufferElementData, System.IEquatable<Game.Vehicles.Passenger>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Passenger;

    public Passenger(Unity.Entities.Entity passenger);

    public System.Boolean Equals(Game.Vehicles.Passenger other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Passenger`  

```csharp
public Unity.Entities.Entity m_Passenger;
```


## Constructors

- `public Passenger(Unity.Entities.Entity passenger)`  

```csharp
public Passenger(Entity passenger)
	{
		m_Passenger = passenger;
	}
```


## Methods

- `public Equals(Game.Vehicles.Passenger other) : System.Boolean`  

```csharp
public bool Equals(Passenger other)
	{
		return m_Passenger.Equals(other.m_Passenger);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Passenger.GetHashCode();
	}
```


