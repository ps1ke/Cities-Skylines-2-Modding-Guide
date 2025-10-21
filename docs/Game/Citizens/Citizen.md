# Game.Citizens.Citizen

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Citizen : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt16 m_PseudoRandom;
    public Game.Citizens.CitizenFlags m_State;
    public System.Byte m_WellBeing;
    public System.Byte m_Health;
    public System.Byte m_LeisureCounter;
    public System.Byte m_PenaltyCounter;
    public System.Int32 m_UnemploymentCounter;
    public System.Int16 m_BirthDay;

    public System.Int32 Happiness { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Citizens.CitizenAge GetAge();
    public System.Single GetAgeInDays(System.UInt32 simulationFrame, Game.Common.TimeData timeData);
    public System.Int32 GetEducationLevel();
    public System.Int32 GetFailedEducationCount();
    public Unity.Mathematics.Random GetPseudoRandom(Game.Citizens.CitizenPseudoRandom reason);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetAge(Game.Citizens.CitizenAge newAge);
    public System.Void SetEducationLevel(System.Int32 level);
    public System.Void SetFailedEducationCount(System.Int32 fails);
}
```


## Fields

- `public System.UInt16 m_PseudoRandom`  

```csharp
public System.UInt16 m_PseudoRandom;
```

- `public Game.Citizens.CitizenFlags m_State`  

```csharp
public Game.Citizens.CitizenFlags m_State;
```

- `public System.Byte m_WellBeing`  

```csharp
public System.Byte m_WellBeing;
```

- `public System.Byte m_Health`  

```csharp
public System.Byte m_Health;
```

- `public System.Byte m_LeisureCounter`  

```csharp
public System.Byte m_LeisureCounter;
```

- `public System.Byte m_PenaltyCounter`  

```csharp
public System.Byte m_PenaltyCounter;
```

- `public System.Int32 m_UnemploymentCounter`  

```csharp
public System.Int32 m_UnemploymentCounter;
```

- `public System.Int16 m_BirthDay`  

```csharp
public System.Int16 m_BirthDay;
```


## Properties

- `public System.Int32 Happiness { get }`  

```csharp
public System.Int32 Happiness { get; }
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetAge() : Game.Citizens.CitizenAge`  

```csharp
public Game.Citizens.CitizenAge GetAge();
```

- `public GetAgeInDays(System.UInt32 simulationFrame, Game.Common.TimeData timeData) : System.Single`  

```csharp
public System.Single GetAgeInDays(System.UInt32 simulationFrame, Game.Common.TimeData timeData);
```

- `public GetEducationLevel() : System.Int32`  

```csharp
public System.Int32 GetEducationLevel();
```

- `public GetFailedEducationCount() : System.Int32`  

```csharp
public System.Int32 GetFailedEducationCount();
```

- `public GetPseudoRandom(Game.Citizens.CitizenPseudoRandom reason) : Unity.Mathematics.Random`  

```csharp
public Unity.Mathematics.Random GetPseudoRandom(Game.Citizens.CitizenPseudoRandom reason);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetAge(Game.Citizens.CitizenAge newAge) : System.Void`  

```csharp
public System.Void SetAge(Game.Citizens.CitizenAge newAge);
```

- `public SetEducationLevel(System.Int32 level) : System.Void`  

```csharp
public System.Void SetEducationLevel(System.Int32 level);
```

- `public SetFailedEducationCount(System.Int32 fails) : System.Void`  

```csharp
public System.Void SetFailedEducationCount(System.Int32 fails);
```


