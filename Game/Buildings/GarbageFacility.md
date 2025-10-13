# Game.Buildings.GarbageFacility

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageFacility : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_GarbageDeliverRequest;
    public Unity.Entities.Entity m_GarbageReceiveRequest;
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Buildings.GarbageFacilityFlags m_Flags;
    public System.Single m_AcceptGarbagePriority;
    public System.Single m_DeliverGarbagePriority;
    public System.Int32 m_ProcessingRate;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_GarbageDeliverRequest`  

```csharp
public Unity.Entities.Entity m_GarbageDeliverRequest;
```

- `public Unity.Entities.Entity m_GarbageReceiveRequest`  

```csharp
public Unity.Entities.Entity m_GarbageReceiveRequest;
```

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Buildings.GarbageFacilityFlags m_Flags`  

```csharp
public Game.Buildings.GarbageFacilityFlags m_Flags;
```

- `public System.Single m_AcceptGarbagePriority`  

```csharp
public System.Single m_AcceptGarbagePriority;
```

- `public System.Single m_DeliverGarbagePriority`  

```csharp
public System.Single m_DeliverGarbagePriority;
```

- `public System.Int32 m_ProcessingRate`  

```csharp
public System.Int32 m_ProcessingRate;
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


