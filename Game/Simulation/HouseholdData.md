# Game.Simulation.CountHouseholdDataSystem+HouseholdData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.IAccumulable<Game.Simulation.CountHouseholdDataSystem+HouseholdData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HouseholdData : Colossal.Collections.IAccumulable<Game.Simulation.CountHouseholdDataSystem+HouseholdData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_MovingInHouseholdCount;
    public System.Int32 m_MovingInCitizenCount;
    public System.Int32 m_MovingAwayHouseholdCount;
    public System.Int32 m_CommuterHouseholdCount;
    public System.Int32 m_TouristCitizenCount;
    public System.Int32 m_HomelessHouseholdCount;
    public System.Int32 m_HomelessCitizenCount;
    public System.Int32 m_MovedInHouseholdCount;
    public System.Int32 m_MovedInCitizenCount;
    public System.Int32 m_ChildrenCount;
    public System.Int32 m_TeenCount;
    public System.Int32 m_AdultCount;
    public System.Int32 m_SeniorCount;
    public System.Int32 m_StudentCount;
    public System.Int32 m_UneducatedCount;
    public System.Int32 m_PoorlyEducatedCount;
    public System.Int32 m_EducatedCount;
    public System.Int32 m_WellEducatedCount;
    public System.Int32 m_HighlyEducatedCount;
    public System.Int32 m_WorkableCitizenCount;
    public System.Int32 m_CityWorkerCount;
    public System.Int32 m_DeadCitizenCount;
    public System.Int64 m_TotalMovedInCitizenHappiness;
    public System.Int64 m_TotalMovedInCitizenWellbeing;
    public System.Int64 m_TotalMovedInCitizenHealth;
    public System.Int32 m_EmployableByEducation0;
    public System.Int32 m_EmployableByEducation1;
    public System.Int32 m_EmployableByEducation2;
    public System.Int32 m_EmployableByEducation3;
    public System.Int32 m_EmployableByEducation4;

    public System.Void Accumulate(Game.Simulation.CountHouseholdDataSystem+HouseholdData other);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Int32 Population();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Int32 Unemployed();
}
```


## Fields

- `public System.Int32 m_MovingInHouseholdCount`  

```csharp
public System.Int32 m_MovingInHouseholdCount;
```

- `public System.Int32 m_MovingInCitizenCount`  

```csharp
public System.Int32 m_MovingInCitizenCount;
```

- `public System.Int32 m_MovingAwayHouseholdCount`  

```csharp
public System.Int32 m_MovingAwayHouseholdCount;
```

- `public System.Int32 m_CommuterHouseholdCount`  

```csharp
public System.Int32 m_CommuterHouseholdCount;
```

- `public System.Int32 m_TouristCitizenCount`  

```csharp
public System.Int32 m_TouristCitizenCount;
```

- `public System.Int32 m_HomelessHouseholdCount`  

```csharp
public System.Int32 m_HomelessHouseholdCount;
```

- `public System.Int32 m_HomelessCitizenCount`  

```csharp
public System.Int32 m_HomelessCitizenCount;
```

- `public System.Int32 m_MovedInHouseholdCount`  

```csharp
public System.Int32 m_MovedInHouseholdCount;
```

- `public System.Int32 m_MovedInCitizenCount`  

```csharp
public System.Int32 m_MovedInCitizenCount;
```

- `public System.Int32 m_ChildrenCount`  

```csharp
public System.Int32 m_ChildrenCount;
```

- `public System.Int32 m_TeenCount`  

```csharp
public System.Int32 m_TeenCount;
```

- `public System.Int32 m_AdultCount`  

```csharp
public System.Int32 m_AdultCount;
```

- `public System.Int32 m_SeniorCount`  

```csharp
public System.Int32 m_SeniorCount;
```

- `public System.Int32 m_StudentCount`  

```csharp
public System.Int32 m_StudentCount;
```

- `public System.Int32 m_UneducatedCount`  

```csharp
public System.Int32 m_UneducatedCount;
```

- `public System.Int32 m_PoorlyEducatedCount`  

```csharp
public System.Int32 m_PoorlyEducatedCount;
```

- `public System.Int32 m_EducatedCount`  

```csharp
public System.Int32 m_EducatedCount;
```

- `public System.Int32 m_WellEducatedCount`  

```csharp
public System.Int32 m_WellEducatedCount;
```

- `public System.Int32 m_HighlyEducatedCount`  

```csharp
public System.Int32 m_HighlyEducatedCount;
```

- `public System.Int32 m_WorkableCitizenCount`  

```csharp
public System.Int32 m_WorkableCitizenCount;
```

- `public System.Int32 m_CityWorkerCount`  

```csharp
public System.Int32 m_CityWorkerCount;
```

- `public System.Int32 m_DeadCitizenCount`  

```csharp
public System.Int32 m_DeadCitizenCount;
```

- `public System.Int64 m_TotalMovedInCitizenHappiness`  

```csharp
public System.Int64 m_TotalMovedInCitizenHappiness;
```

- `public System.Int64 m_TotalMovedInCitizenWellbeing`  

```csharp
public System.Int64 m_TotalMovedInCitizenWellbeing;
```

- `public System.Int64 m_TotalMovedInCitizenHealth`  

```csharp
public System.Int64 m_TotalMovedInCitizenHealth;
```

- `public System.Int32 m_EmployableByEducation0`  

```csharp
public System.Int32 m_EmployableByEducation0;
```

- `public System.Int32 m_EmployableByEducation1`  

```csharp
public System.Int32 m_EmployableByEducation1;
```

- `public System.Int32 m_EmployableByEducation2`  

```csharp
public System.Int32 m_EmployableByEducation2;
```

- `public System.Int32 m_EmployableByEducation3`  

```csharp
public System.Int32 m_EmployableByEducation3;
```

- `public System.Int32 m_EmployableByEducation4`  

```csharp
public System.Int32 m_EmployableByEducation4;
```


## Methods

- `public Accumulate(Game.Simulation.CountHouseholdDataSystem+HouseholdData other) : System.Void`  

```csharp
public System.Void Accumulate(Game.Simulation.CountHouseholdDataSystem+HouseholdData other);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Population() : System.Int32`  

```csharp
public System.Int32 Population();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public Unemployed() : System.Int32`  

```csharp
public System.Int32 Unemployed();
```


