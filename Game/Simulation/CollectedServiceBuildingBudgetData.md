# Game.Simulation.CollectedServiceBuildingBudgetData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CollectedServiceBuildingBudgetData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Count;
    public System.Int32 m_Workers;
    public System.Int32 m_Workplaces;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```

- `public System.Int32 m_Workers`  

```csharp
public System.Int32 m_Workers;
```

- `public System.Int32 m_Workplaces`  

```csharp
public System.Int32 m_Workplaces;
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


