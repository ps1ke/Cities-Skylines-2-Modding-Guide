# Game.Routes.TransportLine

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportLine : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_VehicleRequest;
    public System.Single m_VehicleInterval;
    public System.Single m_UnbunchingFactor;
    public Game.Routes.TransportLineFlags m_Flags;
    public System.UInt16 m_TicketPrice;

    public TransportLine(Game.Prefabs.TransportLineData transportLineData);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_VehicleRequest`  

```csharp
public Unity.Entities.Entity m_VehicleRequest;
```

- `public System.Single m_VehicleInterval`  

```csharp
public System.Single m_VehicleInterval;
```

- `public System.Single m_UnbunchingFactor`  

```csharp
public System.Single m_UnbunchingFactor;
```

- `public Game.Routes.TransportLineFlags m_Flags`  

```csharp
public Game.Routes.TransportLineFlags m_Flags;
```

- `public System.UInt16 m_TicketPrice`  

```csharp
public System.UInt16 m_TicketPrice;
```


## Constructors

- `public TransportLine(Game.Prefabs.TransportLineData transportLineData)`  

```csharp
public TransportLine(TransportLineData transportLineData)
	{
		m_VehicleRequest = Entity.Null;
		m_VehicleInterval = transportLineData.m_DefaultVehicleInterval;
		m_UnbunchingFactor = transportLineData.m_DefaultUnbunchingFactor;
		m_Flags = (TransportLineFlags)0;
		m_TicketPrice = 0;
	}
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


