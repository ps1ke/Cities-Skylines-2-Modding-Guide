# Game.UI.InGame.TaxationUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ITaxSystem m_TaxSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_ResourceQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedZoneQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxRate`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxIncome`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_TaxEffect`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MinTaxRate`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MaxTaxRate`  
- `private Colossal.UI.Binding.RawValueBinding m_AreaTypes`  
- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxRates`  
- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, Colossal.Mathematics.Bounds1> m_AreaResourceTaxRanges`  
- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxIncomes`  
- `private Colossal.UI.Binding.GetterMapBinding<System.Int32, System.Int32> m_AreaTaxEffects`  
- `private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxRates`  
- `private Colossal.UI.Binding.GetterMapBinding<Game.UI.InGame.TaxResource, System.Int32> m_ResourceTaxIncomes`  
- `private Game.Prefabs.TaxParameterData m_CachedTaxParameterData`  
- `private System.Int32 m_CachedLockedOrderVersion`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.String> m_ResourceIcons`  
- `private Game.UI.InGame.TaxationUISystem+TypeHandle __TypeHandle`  
- `private static readonly System.String kGroup`  

## Constructors

- `public TaxationUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetEstimatedResourceTaxIncome(Game.Simulation.TaxAreaType type, System.Int32 resource) : System.Int32`  
- `private GetIcon(Game.Simulation.TaxAreaType type) : System.String`  
- `private GetLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits) : Unity.Mathematics.int2`  
- `private GetResourceLimits(Game.Simulation.TaxAreaType type, Game.Prefabs.TaxParameterData limits) : Unity.Mathematics.int2`  
- `private GetResources(System.Int32 areaType) : System.Collections.Generic.IEnumerable<Game.Prefabs.ResourcePrefab>`  
- `private GetResourceTaxRate(Game.Simulation.TaxAreaType type, System.Int32 resource) : System.Int32`  
- `private Locked(Game.Simulation.TaxAreaType areaType) : System.Boolean`  
- `private MatchArea(Game.Prefabs.TaxableResource data, System.Int32 areaType) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SetAreaTaxRate(System.Int32 areaType, System.Int32 rate) : System.Void`  
- `private SetResourceTaxRate(System.Int32 resource, System.Int32 areaType, System.Int32 rate) : System.Void`  
- `private SetTaxRate(System.Int32 rate) : System.Void`  
- `private UpdateAreaResources(Colossal.UI.Binding.IJsonWriter binder, System.Int32 area) : System.Void`  
- `private UpdateAreaResourceTaxRange(System.Int32 area) : Colossal.Mathematics.Bounds1`  
- `private UpdateAreaTaxEffect(System.Int32 areaType) : System.Int32`  
- `private UpdateAreaTaxIncome(System.Int32 areaType) : System.Int32`  
- `private UpdateAreaTaxRate(System.Int32 areaType) : System.Int32`  
- `private UpdateAreaTypes(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private UpdateMaxTaxRate() : System.Int32`  
- `private UpdateMinTaxRate() : System.Int32`  
- `private UpdateResourceInfo(Game.UI.InGame.TaxResource resource) : Game.UI.InGame.TaxResourceInfo`  
- `private UpdateResourceTaxIncome(Game.UI.InGame.TaxResource taxResource) : System.Int32`  
- `private UpdateResourceTaxRate(Game.UI.InGame.TaxResource taxResource) : System.Int32`  
- `private UpdateTaxEffect() : System.Int32`  
- `private UpdateTaxIncome() : System.Int32`  
- `private UpdateTaxRate() : System.Int32`  

## Nested types

- `Game.UI.InGame.TaxationUISystem+TypeHandle`  
- `Game.UI.InGame.TaxationUISystem+<GetResources>d__46`  

