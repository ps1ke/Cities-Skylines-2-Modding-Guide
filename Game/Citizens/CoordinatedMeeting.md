# Game.Citizens.CoordinatedMeeting

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CoordinatedMeeting : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Citizens.MeetingStatus m_Status;
    public System.Int32 m_Phase;
    public Unity.Entities.Entity m_Target;
    public System.UInt32 m_PhaseEndTime;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Citizens.MeetingStatus m_Status`  

```csharp
public Game.Citizens.MeetingStatus m_Status;
```

- `public System.Int32 m_Phase`  

```csharp
public System.Int32 m_Phase;
```

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public System.UInt32 m_PhaseEndTime`  

```csharp
public System.UInt32 m_PhaseEndTime;
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


