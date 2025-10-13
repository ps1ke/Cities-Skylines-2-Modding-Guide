# Game.Net.GarageLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarageLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt16 m_ParkingFee;
    public System.UInt16 m_ComfortFactor;
    public System.UInt16 m_VehicleCount;
    public System.UInt16 m_VehicleCapacity;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt16 m_ParkingFee`  

```csharp
public System.UInt16 m_ParkingFee;
```

- `public System.UInt16 m_ComfortFactor`  

```csharp
public System.UInt16 m_ComfortFactor;
```

- `public System.UInt16 m_VehicleCount`  

```csharp
public System.UInt16 m_VehicleCount;
```

- `public System.UInt16 m_VehicleCapacity`  

```csharp
public System.UInt16 m_VehicleCapacity;
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


