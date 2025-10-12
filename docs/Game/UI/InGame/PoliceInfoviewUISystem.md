# Game.UI.InGame.PoliceInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimeProducers`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_CrimeProbability`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_JailCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ArrestedCriminals`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InJail`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_PrisonCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Prisoners`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InPrison`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_Criminals`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CrimePerMonth`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_EscapedRate`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_AverageCrimeProbability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_JailAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_PrisonAvailability`  
- `private Unity.Entities.EntityQuery m_PrisonQuery`  
- `private Unity.Entities.EntityQuery m_PrisonModifiedQuery`  
- `private Unity.Entities.EntityQuery m_CriminalQuery`  
- `private Unity.Entities.EntityQuery m_PoliceStationQuery`  
- `private Unity.Entities.EntityQuery m_PoliceStationModifiedQuery`  
- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  
- `private Unity.Entities.EntityQuery m_CrimeProducerModifiedQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_632591896_0`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public PoliceInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetCrimeProbability() : Game.UI.InGame.IndicatorValue`  
- `private GetJailAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetPrisonAvailability() : Game.UI.InGame.IndicatorValue`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  

## Nested types

- `Game.UI.InGame.PoliceInfoviewUISystem+Result`  
- `Game.UI.InGame.PoliceInfoviewUISystem+PoliceStationJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+PrisonJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+CrimeProducerJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+CriminalJob`  
- `Game.UI.InGame.PoliceInfoviewUISystem+TypeHandle`  

