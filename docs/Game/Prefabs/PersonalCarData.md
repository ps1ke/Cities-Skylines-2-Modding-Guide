# Game.Prefabs.PersonalCarData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PersonalCarData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_PassengerCapacity;
    public System.Int32 m_BaggageCapacity;
    public System.Int32 m_CostToDrive;
    public System.Int32 m_Probability;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_PassengerCapacity`  

```csharp
public System.Int32 m_PassengerCapacity;
```

- `public System.Int32 m_BaggageCapacity`  

```csharp
public System.Int32 m_BaggageCapacity;
```

- `public System.Int32 m_CostToDrive`  

```csharp
public System.Int32 m_CostToDrive;
```

- `public System.Int32 m_Probability`  

```csharp
public System.Int32 m_Probability;
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


