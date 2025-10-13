# Game.Areas.Node

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Node : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Position;
    public System.Single m_Elevation;

    public Node(Unity.Mathematics.float3 position, System.Single elevation);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public System.Single m_Elevation`  

```csharp
public System.Single m_Elevation;
```


## Constructors

- `public Node(Unity.Mathematics.float3 position, System.Single elevation)`  

```csharp
public Node(Unity.Mathematics.float3 position, System.Single elevation);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


