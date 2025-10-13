# Game.Simulation.ServiceRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ServiceRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Byte m_FailCount;
    public System.Byte m_Cooldown;
    public Game.Simulation.ServiceRequestFlags m_Flags;

    public ServiceRequest(System.Boolean reversed);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Byte m_FailCount`  

```csharp
public System.Byte m_FailCount;
```

- `public System.Byte m_Cooldown`  

```csharp
public System.Byte m_Cooldown;
```

- `public Game.Simulation.ServiceRequestFlags m_Flags`  

```csharp
public Game.Simulation.ServiceRequestFlags m_Flags;
```


## Constructors

- `public ServiceRequest(System.Boolean reversed)`  

```csharp
public ServiceRequest(System.Boolean reversed);
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


