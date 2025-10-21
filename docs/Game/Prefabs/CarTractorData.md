# Game.Prefabs.CarTractorData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CarTractorData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.CarTrailerType m_TrailerType;
    public Unity.Mathematics.float3 m_AttachPosition;
    public Unity.Entities.Entity m_FixedTrailer;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.CarTrailerType m_TrailerType`  

```csharp
public Game.Prefabs.CarTrailerType m_TrailerType;
```

- `public Unity.Mathematics.float3 m_AttachPosition`  

```csharp
public Unity.Mathematics.float3 m_AttachPosition;
```

- `public Unity.Entities.Entity m_FixedTrailer`  

```csharp
public Unity.Entities.Entity m_FixedTrailer;
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


