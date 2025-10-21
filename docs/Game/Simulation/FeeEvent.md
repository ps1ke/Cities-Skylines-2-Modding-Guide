# Game.Simulation.ServiceFeeSystem+FeeEvent

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FeeEvent : Colossal.Serialization.Entities.ISerializable
{
    public Game.City.PlayerResource m_Resource;
    public System.Single m_Amount;
    public System.Single m_Cost;
    public System.Boolean m_Outside;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.City.PlayerResource m_Resource`  

```csharp
public Game.City.PlayerResource m_Resource;
```

- `public System.Single m_Amount`  

```csharp
public System.Single m_Amount;
```

- `public System.Single m_Cost`  

```csharp
public System.Single m_Cost;
```

- `public System.Boolean m_Outside`  

```csharp
public System.Boolean m_Outside;
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


