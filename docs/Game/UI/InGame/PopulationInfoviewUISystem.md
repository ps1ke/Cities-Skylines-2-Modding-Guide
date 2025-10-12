# Game.UI.InGame.PopulationInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Population`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Employed`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Jobs`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_Unemployment`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_Homelessness`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_BirthRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeathRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedIn`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_MovedAway`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Homeless`  
- `private Colossal.UI.Binding.RawValueBinding m_AgeData`  
- `private Unity.Entities.EntityQuery m_WorkProviderModifiedQuery`  
- `private Unity.Entities.EntityQuery m_PopulationModifiedQuery`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public PopulationInfoviewUISystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private UpdateAgeData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateBindings() : System.Void`  
- `private UpdateStatistics() : System.Void`  

