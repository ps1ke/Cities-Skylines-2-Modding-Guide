# Game.Simulation.WindSimulationSystem+WindCell

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WindCell : Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_Pressure;
    public Unity.Mathematics.float3 m_Velocities;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_Pressure`  

```csharp
public System.Single m_Pressure;
```

- `public Unity.Mathematics.float3 m_Velocities`  

```csharp
public Unity.Mathematics.float3 m_Velocities;
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


