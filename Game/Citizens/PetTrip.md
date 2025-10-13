# Game.Citizens.PetTrip

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct PetTrip : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Source;
    public Unity.Entities.Entity m_Target;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Source`  

```csharp
public Unity.Entities.Entity m_Source;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


