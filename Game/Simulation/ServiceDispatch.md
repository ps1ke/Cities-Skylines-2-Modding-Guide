# Game.Simulation.ServiceDispatch

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ServiceDispatch : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Request;

    public ServiceDispatch(Unity.Entities.Entity request);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Request`  

```csharp
public Unity.Entities.Entity m_Request;
```


## Constructors

- `public ServiceDispatch(Unity.Entities.Entity request)`  

```csharp
public ServiceDispatch(Unity.Entities.Entity request);
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


