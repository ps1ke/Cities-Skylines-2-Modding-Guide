# Game.UI.InGame.HealthcareInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHealth`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCount`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_SickCount`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PatientCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_DeathRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ProcessingRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryUse`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CemeteryCapacity`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_HealthcareAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_DeathcareAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CemeteryAvailability`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Entities.EntityQuery m_DeathcareFacilityQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareFacilityQuery`  
- `private Unity.Entities.EntityQuery m_DeathcareFacilityModifiedQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareFacilityModifiedQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public HealthcareInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetCemeteryAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetDeathcareAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetHealthcareAvailability() : Game.UI.InGame.IndicatorValue`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.HealthcareInfoviewUISystem+Result`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+CalculateAverageHealthJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+UpdateHealthcareJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+UpdateDeathcareJob`  
- `Game.UI.InGame.HealthcareInfoviewUISystem+TypeHandle`  

