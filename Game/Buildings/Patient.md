# Game.Buildings.Patient

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Buildings.Patient>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Patient : Unity.Entities.IBufferElementData, System.IEquatable<Game.Buildings.Patient>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Patient;

    public Patient(Unity.Entities.Entity patient);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Buildings.Patient other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Patient`  

```csharp
public Unity.Entities.Entity m_Patient;
```


## Constructors

- `public Patient(Unity.Entities.Entity patient)`  

```csharp
public Patient(Unity.Entities.Entity patient);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Buildings.Patient other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Buildings.Patient other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


