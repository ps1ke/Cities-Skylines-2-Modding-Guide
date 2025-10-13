# Game.Net.LaneObject

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.LaneObject>`, `System.IComparable<Game.Net.LaneObject>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LaneObject : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.LaneObject>, System.IComparable<Game.Net.LaneObject>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_LaneObject;
    public Unity.Mathematics.float2 m_CurvePosition;

    public LaneObject(Unity.Entities.Entity laneObject);
    public LaneObject(Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);

    public System.Int32 CompareTo(Game.Net.LaneObject other);
    public System.Boolean Equals(Game.Net.LaneObject other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_LaneObject`  

```csharp
public Unity.Entities.Entity m_LaneObject;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```


## Constructors

- `public LaneObject(Unity.Entities.Entity laneObject)`  

```csharp
public LaneObject(Unity.Entities.Entity laneObject);
```

- `public LaneObject(Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition)`  

```csharp
public LaneObject(Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);
```


## Methods

- `public CompareTo(Game.Net.LaneObject other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Net.LaneObject other);
```

- `public Equals(Game.Net.LaneObject other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Net.LaneObject other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


