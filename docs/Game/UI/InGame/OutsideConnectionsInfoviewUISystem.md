# Game.UI.InGame.OutsideConnectionsInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_ResourceQuery`  
- `private Colossal.UI.Binding.RawValueBinding m_TopImportNames`  
- `private Colossal.UI.Binding.RawValueBinding m_TopExportNames`  
- `private Colossal.UI.Binding.RawValueBinding m_TopImportColors`  
- `private Colossal.UI.Binding.RawValueBinding m_TopExportColors`  
- `private Colossal.UI.Binding.RawValueBinding m_TopImportData`  
- `private Colossal.UI.Binding.RawValueBinding m_TopExportData`  
- `private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopImports`  
- `private System.Collections.Generic.List<Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource> m_TopExports`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public OutsideConnectionsInfoviewUISystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private UpdateCache() : System.Void`  
- `private UpdateExportColors(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateExportData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateExportNames(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateImportColors(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateImportData(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateImportNames(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

## Nested types

- `Game.UI.InGame.OutsideConnectionsInfoviewUISystem+TopResource`  

