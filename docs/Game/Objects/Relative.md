# Game.Objects.Relative

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Relative : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;
    public Unity.Mathematics.int3 m_BoneIndex;

    public Relative(Game.Objects.Transform localTransform, Unity.Mathematics.int3 boneIndex);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
    public Game.Objects.Transform ToTransform();
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Unity.Mathematics.int3 m_BoneIndex`  

```csharp
public Unity.Mathematics.int3 m_BoneIndex;
```


## Constructors

- `public Relative(Game.Objects.Transform localTransform, Unity.Mathematics.int3 boneIndex)`  

```csharp
public Relative(Game.Objects.Transform localTransform, Unity.Mathematics.int3 boneIndex);
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

- `public ToTransform() : Game.Objects.Transform`  

```csharp
public Game.Objects.Transform ToTransform();
```


