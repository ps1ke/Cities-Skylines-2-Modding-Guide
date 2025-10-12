# Game.UI.InGame.RoadsInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ParkingCapacity`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkedCars`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ParkingIncome`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ParkingAvailability`  
- `private Unity.Entities.EntityQuery m_ParkingFacilityQuery`  
- `private Unity.Entities.EntityQuery m_ParkingFacilityModifiedQuery`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public RoadsInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  
- `private UpdateAvailability() : System.Void`  
- `private UpdateCapacity() : System.Void`  
- `private UpdateIncome() : System.Void`  

## Nested types

- `Game.UI.InGame.RoadsInfoviewUISystem+Result`  
- `Game.UI.InGame.RoadsInfoviewUISystem+UpdateParkingJob`  
- `Game.UI.InGame.RoadsInfoviewUISystem+TypeHandle`  

