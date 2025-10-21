# Game.Zones.Block

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Zones.Block>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Block : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Zones.Block>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float2 m_Direction;
    public Unity.Mathematics.int2 m_Size;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Zones.Block other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float2 m_Direction`  

```csharp
public Unity.Mathematics.float2 m_Direction;
```

- `public Unity.Mathematics.int2 m_Size`  

```csharp
public Unity.Mathematics.int2 m_Size;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Zones.Block other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Zones.Block other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


