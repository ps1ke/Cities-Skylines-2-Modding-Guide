# Game.Simulation.CollectedCityServiceBudgetData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CollectedCityServiceBudgetData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.int3 m_Workplaces;
    public System.Int32 m_Count;
    public System.Int32 m_Export;
    public System.Int32 m_BaseCost;
    public System.Int32 m_Wages;
    public System.Int32 m_FullWages;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.int3 m_Workplaces`  

```csharp
public Unity.Mathematics.int3 m_Workplaces;
```

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```

- `public System.Int32 m_Export`  

```csharp
public System.Int32 m_Export;
```

- `public System.Int32 m_BaseCost`  

```csharp
public System.Int32 m_BaseCost;
```

- `public System.Int32 m_Wages`  

```csharp
public System.Int32 m_Wages;
```

- `public System.Int32 m_FullWages`  

```csharp
public System.Int32 m_FullWages;
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


