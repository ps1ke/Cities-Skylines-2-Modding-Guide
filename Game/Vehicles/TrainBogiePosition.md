# Game.Vehicles.TrainBogiePosition

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrainBogiePosition : Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Direction;

    public TrainBogiePosition(Game.Objects.Transform transform);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Direction`  

```csharp
public Unity.Mathematics.float3 m_Direction;
```


## Constructors

- `public TrainBogiePosition(Game.Objects.Transform transform)`  

```csharp
public TrainBogiePosition(Game.Objects.Transform transform);
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


