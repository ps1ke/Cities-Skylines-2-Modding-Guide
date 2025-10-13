# Game.Zones.VacantLot

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Zones.VacantLot>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct VacantLot : Unity.Entities.IBufferElementData, System.IEquatable<Game.Zones.VacantLot>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.int4 m_Area;
    public Game.Zones.ZoneType m_Type;
    public System.Int16 m_Height;
    public Game.Zones.LotFlags m_Flags;

    public VacantLot(Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, Game.Zones.ZoneType type, System.Int32 height, Game.Zones.LotFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Zones.VacantLot other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.int4 m_Area`  

```csharp
public Unity.Mathematics.int4 m_Area;
```

- `public Game.Zones.ZoneType m_Type`  

```csharp
public Game.Zones.ZoneType m_Type;
```

- `public System.Int16 m_Height`  

```csharp
public System.Int16 m_Height;
```

- `public Game.Zones.LotFlags m_Flags`  

```csharp
public Game.Zones.LotFlags m_Flags;
```


## Constructors

- `public VacantLot(Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, Game.Zones.ZoneType type, System.Int32 height, Game.Zones.LotFlags flags)`  

```csharp
public VacantLot(Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, Game.Zones.ZoneType type, System.Int32 height, Game.Zones.LotFlags flags);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Zones.VacantLot other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Zones.VacantLot other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


