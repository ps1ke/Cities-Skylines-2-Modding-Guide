# Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ResidentialPropertyData : Colossal.Collections.IAccumulable<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.int3 m_FreeProperties;
    public Unity.Mathematics.int3 m_TotalProperties;
    public System.Int32 m_FreeShelterCapacity;
    public System.Int32 m_TotalShelterCapacity;

    public System.Void Accumulate(Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData other);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.int3 m_FreeProperties`  

```csharp
public Unity.Mathematics.int3 m_FreeProperties;
```

- `public Unity.Mathematics.int3 m_TotalProperties`  

```csharp
public Unity.Mathematics.int3 m_TotalProperties;
```

- `public System.Int32 m_FreeShelterCapacity`  

```csharp
public System.Int32 m_FreeShelterCapacity;
```

- `public System.Int32 m_TotalShelterCapacity`  

```csharp
public System.Int32 m_TotalShelterCapacity;
```


## Methods

- `public Accumulate(Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData other) : System.Void`  

```csharp
public System.Void Accumulate(Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData other);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


