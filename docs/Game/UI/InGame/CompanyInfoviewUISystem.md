# Game.UI.InGame.CompanyInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityQuery m_CommercialQuery`  
- `private Unity.Entities.EntityQuery m_IndustrialQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_CommercialProfitability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_IndustrialProfitability`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_OfficeProfitability`  
- `private Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public CompanyInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetCommercialProfitability() : Game.UI.InGame.IndicatorValue`  
- `private GetIndustrialProfitability() : Game.UI.InGame.IndicatorValue`  
- `private GetOfficeProfitability() : Game.UI.InGame.IndicatorValue`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.CompanyInfoviewUISystem+TypeHandle`  

