# Game.Zones.ZoneType

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Zones.ZoneType>`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ZoneType : System.IEquatable<Game.Zones.ZoneType>, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt16 m_Index;

    public static Game.Zones.ZoneType None { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Zones.ZoneType other);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt16 m_Index`  

```csharp
public System.UInt16 m_Index;
```


## Properties

- `public static Game.Zones.ZoneType None { get }`  

```csharp
public static Game.Zones.ZoneType None { get; }
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Zones.ZoneType other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Zones.ZoneType other);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


