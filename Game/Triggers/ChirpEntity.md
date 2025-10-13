# Game.Triggers.ChirpEntity

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ChirpEntity : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Entity;

    public ChirpEntity(Unity.Entities.Entity entity);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```


## Constructors

- `public ChirpEntity(Unity.Entities.Entity entity)`  

```csharp
public ChirpEntity(Unity.Entities.Entity entity);
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


