# Game.Creatures.Queue

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Queue : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetEntity;
    public Colossal.Mathematics.Sphere3 m_TargetArea;
    public System.UInt16 m_ObsoleteTime;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetEntity`  

```csharp
public Unity.Entities.Entity m_TargetEntity;
```

- `public Colossal.Mathematics.Sphere3 m_TargetArea`  

```csharp
public Colossal.Mathematics.Sphere3 m_TargetArea;
```

- `public System.UInt16 m_ObsoleteTime`  

```csharp
public System.UInt16 m_ObsoleteTime;
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


