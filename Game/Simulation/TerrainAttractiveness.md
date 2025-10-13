# Game.Simulation.TerrainAttractiveness

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TerrainAttractiveness : Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ShoreBonus;
    public System.Single m_ForestBonus;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ShoreBonus`  

```csharp
public System.Single m_ShoreBonus;
```

- `public System.Single m_ForestBonus`  

```csharp
public System.Single m_ForestBonus;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


