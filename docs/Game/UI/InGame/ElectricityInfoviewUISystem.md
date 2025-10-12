# Game.UI.InGame.ElectricityInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ElectricityStatisticsSystem m_ElectricityStatisticsSystem`  
- `private Game.Simulation.ElectricityTradeSystem m_ElectricityTradeSystem`  
- `private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityProduction`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityConsumption`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityTransmitted`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityExport`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityImport`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityAvailability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTransmission`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTrade`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_BatteryCharge`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public ElectricityInfoviewUISystem()`  

## Methods

- `private <OnCreate>b__13_0() : System.Int32`  
- `private <OnCreate>b__13_1() : System.Int32`  
- `private <OnCreate>b__13_2() : System.Int32`  
- `private <OnCreate>b__13_3() : System.Int32`  
- `private <OnCreate>b__13_4() : System.Int32`  
- `private GetBatteryCharge() : Game.UI.InGame.IndicatorValue`  
- `private GetElectricityAvailability() : Game.UI.InGame.IndicatorValue`  
- `private GetElectricityTrade() : Game.UI.InGame.IndicatorValue`  
- `private GetElectricityTransmission() : Game.UI.InGame.IndicatorValue`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

