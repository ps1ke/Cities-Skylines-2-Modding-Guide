# Game.Simulation.WaterSourceData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterSourceData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_ConstantDepth;
    public System.Single m_Amount;
    public System.Single m_Radius;
    public System.Single m_Multiplier;
    public System.Single m_Polluted;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_ConstantDepth`  

```csharp
public System.Int32 m_ConstantDepth;
```

- `public System.Single m_Amount`  

```csharp
public System.Single m_Amount;
```

- `public System.Single m_Radius`  

```csharp
public System.Single m_Radius;
```

- `public System.Single m_Multiplier`  

```csharp
public System.Single m_Multiplier;
```

- `public System.Single m_Polluted`  

```csharp
public System.Single m_Polluted;
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


