# Game.Events.InvolvedInAccident

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct InvolvedInAccident : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Event;
    public System.Single m_Severity;
    public System.UInt32 m_InvolvedFrame;

    public InvolvedInAccident(Unity.Entities.Entity _event, System.Single severity, System.UInt32 simulationFrame);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public System.Single m_Severity`  

```csharp
public System.Single m_Severity;
```

- `public System.UInt32 m_InvolvedFrame`  

```csharp
public System.UInt32 m_InvolvedFrame;
```


## Constructors

- `public InvolvedInAccident(Unity.Entities.Entity _event, System.Single severity, System.UInt32 simulationFrame)`  

```csharp
public InvolvedInAccident(Unity.Entities.Entity _event, System.Single severity, System.UInt32 simulationFrame);
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


