# Game.Areas.Extractor

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Extractor : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ResourceAmount;
    public System.Single m_MaxConcentration;
    public System.Single m_ExtractedAmount;
    public System.Single m_WorkAmount;
    public System.Single m_HarvestedAmount;
    public System.Single m_TotalExtracted;
    public Game.Vehicles.VehicleWorkType m_WorkType;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ResourceAmount`  

```csharp
public System.Single m_ResourceAmount;
```

- `public System.Single m_MaxConcentration`  

```csharp
public System.Single m_MaxConcentration;
```

- `public System.Single m_ExtractedAmount`  

```csharp
public System.Single m_ExtractedAmount;
```

- `public System.Single m_WorkAmount`  

```csharp
public System.Single m_WorkAmount;
```

- `public System.Single m_HarvestedAmount`  

```csharp
public System.Single m_HarvestedAmount;
```

- `public System.Single m_TotalExtracted`  

```csharp
public System.Single m_TotalExtracted;
```

- `public Game.Vehicles.VehicleWorkType m_WorkType`  

```csharp
public Game.Vehicles.VehicleWorkType m_WorkType;
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


