# Game.Simulation.HealthcareRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HealthcareRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Citizen;
    public Game.Simulation.HealthcareRequestType m_Type;

    public HealthcareRequest(Unity.Entities.Entity citizen, Game.Simulation.HealthcareRequestType type);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Citizen`  

```csharp
public Unity.Entities.Entity m_Citizen;
```

- `public Game.Simulation.HealthcareRequestType m_Type`  

```csharp
public Game.Simulation.HealthcareRequestType m_Type;
```


## Constructors

- `public HealthcareRequest(Unity.Entities.Entity citizen, Game.Simulation.HealthcareRequestType type)`  

```csharp
public HealthcareRequest(Unity.Entities.Entity citizen, Game.Simulation.HealthcareRequestType type);
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


