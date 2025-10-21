# Game.Net.ParkingLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ParkingLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_AccessRestriction;
    public Game.Pathfind.PathNode m_SecondaryStartNode;
    public Game.Net.ParkingLaneFlags m_Flags;
    public System.Single m_FreeSpace;
    public System.UInt16 m_ParkingFee;
    public System.UInt16 m_ComfortFactor;
    public System.UInt16 m_TaxiAvailability;
    public System.UInt16 m_TaxiFee;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_AccessRestriction`  

```csharp
public Unity.Entities.Entity m_AccessRestriction;
```

- `public Game.Pathfind.PathNode m_SecondaryStartNode`  

```csharp
public Game.Pathfind.PathNode m_SecondaryStartNode;
```

- `public Game.Net.ParkingLaneFlags m_Flags`  

```csharp
public Game.Net.ParkingLaneFlags m_Flags;
```

- `public System.Single m_FreeSpace`  

```csharp
public System.Single m_FreeSpace;
```

- `public System.UInt16 m_ParkingFee`  

```csharp
public System.UInt16 m_ParkingFee;
```

- `public System.UInt16 m_ComfortFactor`  

```csharp
public System.UInt16 m_ComfortFactor;
```

- `public System.UInt16 m_TaxiAvailability`  

```csharp
public System.UInt16 m_TaxiAvailability;
```

- `public System.UInt16 m_TaxiFee`  

```csharp
public System.UInt16 m_TaxiFee;
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


