# Game.Simulation.GarbageTransferRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageTransferRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Facility;
    public Game.Simulation.GarbageTransferRequestFlags m_Flags;
    public System.Single m_Priority;
    public System.Int32 m_Amount;

    public GarbageTransferRequest(Unity.Entities.Entity facility, Game.Simulation.GarbageTransferRequestFlags flags, System.Single priority, System.Int32 amount);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Facility`  

```csharp
public Unity.Entities.Entity m_Facility;
```

- `public Game.Simulation.GarbageTransferRequestFlags m_Flags`  

```csharp
public Game.Simulation.GarbageTransferRequestFlags m_Flags;
```

- `public System.Single m_Priority`  

```csharp
public System.Single m_Priority;
```

- `public System.Int32 m_Amount`  

```csharp
public System.Int32 m_Amount;
```


## Constructors

- `public GarbageTransferRequest(Unity.Entities.Entity facility, Game.Simulation.GarbageTransferRequestFlags flags, System.Single priority, System.Int32 amount)`  

```csharp
public GarbageTransferRequest(Unity.Entities.Entity facility, Game.Simulation.GarbageTransferRequestFlags flags, System.Single priority, System.Int32 amount);
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


