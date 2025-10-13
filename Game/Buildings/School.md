# Game.Buildings.School

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct School : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_AverageGraduationTime;
    public System.Single m_AverageFailProbability;
    public System.SByte m_StudentWellbeing;
    public System.SByte m_StudentHealth;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_AverageGraduationTime`  

```csharp
public System.Single m_AverageGraduationTime;
```

- `public System.Single m_AverageFailProbability`  

```csharp
public System.Single m_AverageFailProbability;
```

- `public System.SByte m_StudentWellbeing`  

```csharp
public System.SByte m_StudentWellbeing;
```

- `public System.SByte m_StudentHealth`  

```csharp
public System.SByte m_StudentHealth;
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


