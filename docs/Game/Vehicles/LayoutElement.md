# Game.Vehicles.LayoutElement

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Vehicles.LayoutElement>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LayoutElement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Vehicles.LayoutElement>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Vehicle;

    public LayoutElement(Unity.Entities.Entity vehicle);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Vehicles.LayoutElement other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Vehicle`  

```csharp
public Unity.Entities.Entity m_Vehicle;
```


## Constructors

- `public LayoutElement(Unity.Entities.Entity vehicle)`  

```csharp
public LayoutElement(Unity.Entities.Entity vehicle);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Vehicles.LayoutElement other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Vehicles.LayoutElement other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


