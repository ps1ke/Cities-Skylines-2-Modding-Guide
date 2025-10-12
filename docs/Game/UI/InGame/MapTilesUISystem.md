# Game.UI.InGame.MapTilesUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.MapTilePurchaseSystem m_MapTileSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesPanelVisibleBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesViewActiveBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ResourcesBinding`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_BuildableLandBinding`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_WaterBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchasePriceBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseUpkeepBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseFlagsBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitsBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitCostBinding`  
- `private System.Int32 m_LastSelected`  
- `private System.Boolean m_IsLastTimeZoomOut`  
- `private static System.Boolean <mapTileViewActive>k__BackingField`  
- `private static const System.String kGroup`  

## Properties

- `public static System.Boolean mapTileViewActive { get; private set }`  

## Constructors

- `public MapTilesUISystem()`  

## Methods

- `private <OnCreate>b__22_0() : System.Boolean`  
- `private <OnCreate>b__22_2() : System.Int32`  
- `private <OnCreate>b__22_3() : System.Int32`  
- `private <OnCreate>b__22_4() : System.Int32`  
- `private <OnCreate>b__22_5() : System.Int32`  
- `private <OnCreate>b__22_6() : System.Int32`  
- `private BindResources(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private GetResource(Game.Areas.MapFeature feature) : Game.UI.InGame.MapTilesUISystem+UIMapTileResource`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private PurchaseMapTiles() : System.Void`  
- `private SetMapTileViewActive(System.Boolean enabled) : System.Void`  

## Nested types

- `Game.UI.InGame.MapTilesUISystem+UIMapTileResource`  
- `Game.UI.InGame.MapTilesUISystem+<>c`  

