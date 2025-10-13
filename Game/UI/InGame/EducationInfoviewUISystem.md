# Game.UI.InGame.EducationInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EducationInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Colossal.UI.Binding.RawValueBinding m_EducationData;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_SchoolQuery;
    private Unity.Entities.EntityQuery m_SchoolModifiedQuery;
    private Unity.Entities.EntityQuery m_EligibleQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_607537787_0;
    private Unity.Entities.EntityQuery __query_607537787_1;
    private Unity.Entities.EntityQuery __query_607537787_2;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public EducationInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
    private Game.UI.InGame.IndicatorValue UpdateCollegeAvailability();
    private System.Void UpdateEducationData(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.IndicatorValue UpdateElementaryAvailability();
    private System.Void UpdateEligibility();
    private Game.UI.InGame.IndicatorValue UpdateHighSchoolAvailability();
    private System.Void UpdateStudentCounts();
    private Game.UI.InGame.IndicatorValue UpdateUniversityAvailability();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_EducationData`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_EducationData;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_SchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolQuery;
```

- `private Unity.Entities.EntityQuery m_SchoolModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_EligibleQuery`  

```csharp
private Unity.Entities.EntityQuery m_EligibleQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_607537787_0`  

```csharp
private Unity.Entities.EntityQuery __query_607537787_0;
```

- `private Unity.Entities.EntityQuery __query_607537787_1`  

```csharp
private Unity.Entities.EntityQuery __query_607537787_1;
```

- `private Unity.Entities.EntityQuery __query_607537787_2`  

```csharp
private Unity.Entities.EntityQuery __query_607537787_2;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public EducationInfoviewUISystem()`  

```csharp
public EducationInfoviewUISystem();
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

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```

- `private ResetResults() : System.Void`  

```csharp
private System.Void ResetResults();
```

- `private UpdateCollegeAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue UpdateCollegeAvailability();
```

- `private UpdateEducationData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateEducationData(Colossal.UI.Binding.IJsonWriter binder);
```

- `private UpdateElementaryAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue UpdateElementaryAvailability();
```

- `private UpdateEligibility() : System.Void`  

```csharp
private System.Void UpdateEligibility();
```

- `private UpdateHighSchoolAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue UpdateHighSchoolAvailability();
```

- `private UpdateStudentCounts() : System.Void`  

```csharp
private System.Void UpdateStudentCounts();
```

- `private UpdateUniversityAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue UpdateUniversityAvailability();
```


## Nested types

- `Game.UI.InGame.EducationInfoviewUISystem+Result`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateEducationDataJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateStudentCountsJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateEligibilityJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+TypeHandle`  

