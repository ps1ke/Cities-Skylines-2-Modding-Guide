# Game.UI.InGame.EducationInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Colossal.UI.Binding.RawValueBinding m_EducationData`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryStudents`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolStudents`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeStudents`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityStudents`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryEligible`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolEligible`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeEligible`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityEligible`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ElementaryCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_HighSchoolCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollegeCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_UniversityCapacity`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElementaryAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HighSchoolAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CollegeAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_UniversityAvailability`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_SchoolQuery`  
- `private Unity.Entities.EntityQuery m_SchoolModifiedQuery`  
- `private Unity.Entities.EntityQuery m_EligibleQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Game.UI.InGame.EducationInfoviewUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_607537787_0`  
- `private Unity.Entities.EntityQuery __query_607537787_1`  
- `private Unity.Entities.EntityQuery __query_607537787_2`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public EducationInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  
- `private UpdateCollegeAvailability() : Game.UI.InGame.IndicatorValue`  
- `private UpdateEducationData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateElementaryAvailability() : Game.UI.InGame.IndicatorValue`  
- `private UpdateEligibility() : System.Void`  
- `private UpdateHighSchoolAvailability() : Game.UI.InGame.IndicatorValue`  
- `private UpdateStudentCounts() : System.Void`  
- `private UpdateUniversityAvailability() : Game.UI.InGame.IndicatorValue`  

## Nested types

- `Game.UI.InGame.EducationInfoviewUISystem+Result`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateEducationDataJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateStudentCountsJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+UpdateEligibilityJob`  
- `Game.UI.InGame.EducationInfoviewUISystem+TypeHandle`  

