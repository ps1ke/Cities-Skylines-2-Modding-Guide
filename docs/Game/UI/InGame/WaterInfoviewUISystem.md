# Game.UI.InGame.WaterInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterCapacity`  
- `private Game.Simulation.WaterTradeSystem m_WaterTradeSystem`  
- `private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterConsumption`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageCapacity`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageConsumption`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterExport`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterImport`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_SewageAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageExport`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterTrade`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public WaterInfoviewUISystem()`  

## Methods

- `private <OnCreate>b__14_0() : System.Int32`  
- `private <OnCreate>b__14_1() : System.Int32`  
- `private <OnCreate>b__14_2() : System.Int32`  
- `private <OnCreate>b__14_3() : System.Int32`  
- `private <OnCreate>b__14_4() : System.Int32`  
- `private <OnCreate>b__14_5() : System.Int32`  
- `private <OnCreate>b__14_6() : System.Int32`  
- `private GetSewageAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetWaterAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetWaterTrade() : Game.UI.InGame.IndicatorValue`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

