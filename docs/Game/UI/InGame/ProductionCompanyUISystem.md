# Game.UI.InGame.ProductionCompanyUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.IBudgetSystem m_BudgetSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private System.Collections.Generic.Dictionary<System.String, Game.Economy.Resource> m_ResourceIDMap`  
- `private Colossal.UI.Binding.RawValueBinding m_ProductionCompanyInfoBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_IndustrialCompanyWealthBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CommercialCompanyWealthBinding`  
- `private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_CachedValues`  
- `private Unity.Collections.NativeArray<Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo> m_Values`  
- `private Game.Economy.Resource m_SelectedResource`  
- `private Unity.Collections.NativeQueue<Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo> m_ProductionCompanyInfoQueue`  
- `private Unity.Entities.EntityQuery m_CompanyQuery`  
- `private Game.UI.InGame.ProductionCompanyUISystem+TypeHandle __TypeHandle`  
- `private static readonly System.String kGroup`  
- `private static readonly System.Int32 kLevels`  

## Constructors

- `public ProductionCompanyUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnSelectResource(System.String resourceID) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Patch(System.Int32 index, System.String fieldName, System.Int32 value) : System.Void`  
- `private PatchProductionCompanyInfo() : System.Void`  
- `private RebuildResourceIDMap() : System.Void`  
- `private UpdateProductionCompanyInfo(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

## Nested types

- `Game.UI.InGame.ProductionCompanyUISystem+MapCompanyStatisticsJob`  
- `Game.UI.InGame.ProductionCompanyUISystem+ProductionCompanyInfo`  
- `Game.UI.InGame.ProductionCompanyUISystem+ProductionLevelInfo`  
- `Game.UI.InGame.ProductionCompanyUISystem+TypeHandle`  

