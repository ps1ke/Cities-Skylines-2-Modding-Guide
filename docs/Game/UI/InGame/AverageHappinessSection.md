# Game.UI.InGame.AverageHappinessSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AverageHappinessSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
    public Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.CitizenHappiness <averageHappiness>k__BackingField;
    private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <happinessFactors>k__BackingField;
    protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    protected Unity.Entities.EntityQuery m_GarbageParameterQuery;
    protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
    protected Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    protected Unity.Entities.EntityQuery m_ParkParameterQuery;
    protected Unity.Entities.EntityQuery m_EducationParameterQuery;
    protected Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Game.UI.InGame.AverageHappinessSection+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1244325462_0;

    protected System.String group { protected get; }
    private Game.UI.InGame.CitizenHappiness averageHappiness { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> happinessFactors { private get; private set; }

    public AverageHappinessSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private static System.Boolean TryAddPropertyHappiness(System.Int32& happiness, System.Int32& citizenCount, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> healthProblemFromEntity, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterFromEntity, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizenFromEntity);
}
```


## Fields

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictBuildingQuery;
```

- `public Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.CitizenHappiness <averageHappiness>k__BackingField`  

```csharp
private Game.UI.InGame.CitizenHappiness <averageHappiness>k__BackingField;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <happinessFactors>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <happinessFactors>k__BackingField;
```

- `protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `private Game.UI.InGame.AverageHappinessSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.AverageHappinessSection+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1244325462_0`  

```csharp
private Unity.Entities.EntityQuery __query_1244325462_0;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.CitizenHappiness averageHappiness { private get; private set }`  

```csharp
private Game.UI.InGame.CitizenHappiness averageHappiness { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> happinessFactors { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> happinessFactors { private get; private set; }
```


## Constructors

- `public AverageHappinessSection()`  

```csharp
public AverageHappinessSection();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private static TryAddPropertyHappiness(System.Int32& happiness, System.Int32& citizenCount, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> healthProblemFromEntity, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterFromEntity, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizenFromEntity) : System.Boolean`  

```csharp
private static System.Boolean TryAddPropertyHappiness(System.Int32& happiness, System.Int32& citizenCount, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Citizens.Household> householdFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizenFromEntity, Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> healthProblemFromEntity, Unity.Entities.BufferLookup<Game.Buildings.Renter> renterFromEntity, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizenFromEntity);
```


## Nested types

- `Game.UI.InGame.AverageHappinessSection+Result`  
- `Game.UI.InGame.AverageHappinessSection+CountHappinessJob`  
- `Game.UI.InGame.AverageHappinessSection+CountDistrictHappinessJob`  
- `Game.UI.InGame.AverageHappinessSection+TypeHandle`  

