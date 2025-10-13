# Game.Objects.BlockedLane

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Objects.BlockedLane>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct BlockedLane : Unity.Entities.IBufferElementData, System.IEquatable<Game.Objects.BlockedLane>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Lane;
    public Unity.Mathematics.float2 m_CurvePosition;

    public BlockedLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePosition);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Objects.BlockedLane other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```


## Constructors

- `public BlockedLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePosition)`  

```csharp
public BlockedLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePosition);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Objects.BlockedLane other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Objects.BlockedLane other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


