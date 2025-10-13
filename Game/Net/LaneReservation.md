# Game.Net.LaneReservation

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LaneReservation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Blocker;
    public Game.Net.ReservationData m_Next;
    public Game.Net.ReservationData m_Prev;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetOffset();
    public System.Int32 GetPriority();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public Game.Net.ReservationData m_Next`  

```csharp
public Game.Net.ReservationData m_Next;
```

- `public Game.Net.ReservationData m_Prev`  

```csharp
public Game.Net.ReservationData m_Prev;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetOffset() : System.Single`  

```csharp
public float GetOffset()
	{
		return (float)math.max((int)m_Next.m_Offset, (int)m_Prev.m_Offset) * 0.003921569f;
	}
```

- `public GetPriority() : System.Int32`  

```csharp
public int GetPriority()
	{
		return math.max((int)m_Next.m_Priority, (int)m_Prev.m_Priority);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


