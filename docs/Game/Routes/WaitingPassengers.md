# Game.Routes.WaitingPassengers

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaitingPassengers : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Count;
    public System.Int32 m_OngoingAccumulation;
    public System.Int32 m_ConcludedAccumulation;
    public System.UInt16 m_SuccessAccumulation;
    public System.UInt16 m_AverageWaitingTime;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```

- `public System.Int32 m_OngoingAccumulation`  

```csharp
public System.Int32 m_OngoingAccumulation;
```

- `public System.Int32 m_ConcludedAccumulation`  

```csharp
public System.Int32 m_ConcludedAccumulation;
```

- `public System.UInt16 m_SuccessAccumulation`  

```csharp
public System.UInt16 m_SuccessAccumulation;
```

- `public System.UInt16 m_AverageWaitingTime`  

```csharp
public System.UInt16 m_AverageWaitingTime;
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


