# Game.UI.InGame.GarbageInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability`  
- `private Unity.Entities.EntityQuery m_GarbageFacilityQuery`  
- `private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public GarbageInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <OnCreate>b__11_0() : System.Single`  
- `private GetGarbageCapacity() : System.Int32`  
- `private GetLandfillAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetProcessingAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetProcessingRate() : System.Single`  
- `private GetStoredGarbage() : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  

## Nested types

- `Game.UI.InGame.GarbageInfoviewUISystem+Result`  
- `Game.UI.InGame.GarbageInfoviewUISystem+UpdateGarbageJob`  
- `Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle`  

