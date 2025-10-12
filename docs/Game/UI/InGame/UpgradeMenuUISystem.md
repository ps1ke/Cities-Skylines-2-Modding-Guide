# Game.UI.InGame.UpgradeMenuUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery`  
- `private Unity.Entities.EntityQuery m_CreatedExtensionQuery`  
- `private Unity.Entities.EntityQuery m_DeletedExtensionQuery`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultTool`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Tools.NetToolSystem m_NetToolSystem`  
- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  
- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem`  
- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  
- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades`  
- `private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules`  
- `private System.Boolean m_UniqueAssetStatusChanged`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `public System.Boolean upgrading { get }`  

## Constructors

- `public UpgradeMenuUISystem()`  

## Methods

- `private BindUpgradeDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgrade) : System.Void`  
- `private BindUpgrades(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgradable) : System.Void`  
- `private CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity) : System.ValueTuple<System.Boolean, System.Boolean>`  
- `private ClearUpgradeSelection() : System.Void`  
- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnStopRunning() : System.Void`  
- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  
- `private OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SelectUpgrade(Unity.Entities.Entity upgradable, Unity.Entities.Entity upgrade) : System.Void`  

## Nested types

- `Game.UI.InGame.UpgradeMenuUISystem+SortableEntity`  

