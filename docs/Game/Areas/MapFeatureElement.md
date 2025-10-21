# Game.Areas.MapFeatureElement

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct MapFeatureElement : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Amount;
    public System.Single m_RenewalRate;

    public MapFeatureElement(System.Single amount, System.Single regenerationRate);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Amount`  

```csharp
public System.Single m_Amount;
```

- `public System.Single m_RenewalRate`  

```csharp
public System.Single m_RenewalRate;
```


## Constructors

- `public MapFeatureElement(System.Single amount, System.Single regenerationRate)`  

```csharp
public MapFeatureElement(System.Single amount, System.Single regenerationRate);
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


