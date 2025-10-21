# Game.Objects.TransformFrame

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct TransformFrame : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_Velocity;
    public Unity.Mathematics.quaternion m_Rotation;
    public Game.Objects.TransformFlags m_Flags;
    public System.UInt16 m_StateTimer;
    public Game.Objects.TransformState m_State;
    public System.Byte m_Activity;

    public TransformFrame(Game.Objects.Transform transform);
    public TransformFrame(Game.Objects.Transform transform, Game.Objects.Moving moving);
    public TransformFrame(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 velocity);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_Velocity`  

```csharp
public Unity.Mathematics.float3 m_Velocity;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Game.Objects.TransformFlags m_Flags`  

```csharp
public Game.Objects.TransformFlags m_Flags;
```

- `public System.UInt16 m_StateTimer`  

```csharp
public System.UInt16 m_StateTimer;
```

- `public Game.Objects.TransformState m_State`  

```csharp
public Game.Objects.TransformState m_State;
```

- `public System.Byte m_Activity`  

```csharp
public System.Byte m_Activity;
```


## Constructors

- `public TransformFrame(Game.Objects.Transform transform)`  

```csharp
public TransformFrame(Game.Objects.Transform transform);
```

- `public TransformFrame(Game.Objects.Transform transform, Game.Objects.Moving moving)`  

```csharp
public TransformFrame(Game.Objects.Transform transform, Game.Objects.Moving moving);
```

- `public TransformFrame(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 velocity)`  

```csharp
public TransformFrame(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 velocity);
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


