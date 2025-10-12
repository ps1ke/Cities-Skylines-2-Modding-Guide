# Game.UI.InGame.ToolbarUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultTool`  
- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private Game.UI.InGame.UpgradeMenuUISystem m_UpgradeMenuUISystem`  
- `private Game.UI.InGame.ActionsSection m_ActionsSection`  
- `private Unity.Entities.EntityQuery m_ThemeQuery`  
- `private Unity.Entities.EntityQuery m_AssetPackQuery`  
- `private Unity.Entities.EntityQuery m_ToolbarGroupQuery`  
- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  
- `private Colossal.UI.Binding.RawValueBinding m_ToolbarGroupsBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetMenuCategoriesBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_ThemesBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_AssetPacksBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_AgeMaskBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedThemesBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedAssetPacksBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetMenuBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetCategoryBinding`  
- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetBinding`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedCategories`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedAssets`  
- `private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedThemes`  
- `private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedAssetPacks`  
- `private System.Boolean m_UniqueAssetStatusChanged`  
- `private System.Boolean m_HasUnlockedPrefabLastFrame`  
- `private static const System.String kGroup`  

## Properties

- `public System.Boolean hasActiveSelection { get }`  

## Constructors

- `public ToolbarUISystem()`  

## Methods

- `private <OnCreate>b__34_0() : System.Collections.Generic.List<Unity.Entities.Entity>`  
- `private <OnCreate>b__34_1() : System.Collections.Generic.List<Unity.Entities.Entity>`  
- `private ActivatePrefabTool(Unity.Entities.Entity assetEntity) : System.Void`  
- `private Apply(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity, System.Boolean updateTool = False) : System.Void`  
- `public BindAsset(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique = False, System.Boolean placed = False) : System.Void`  
- `private BindAssetCategories(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetMenu) : System.Void`  
- `private BindAssets(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetCategory) : System.Void`  
- `private BindPacks(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindThemes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindToolbarGroups(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `public ClearAssetSelection() : System.Void`  
- `private ClearAssetSelection(System.Boolean updateTool) : System.Void`  
- `private FilterByPack(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity packEntity) : System.Void`  
- `private FilterByPacks(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> packs) : System.Void`  
- `private FilterByTheme(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity themeEntity) : System.Void`  
- `private FilterByThemes(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> themes) : System.Void`  
- `private FilterOutUpgrades(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos) : System.Void`  
- `private FilterPacksByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> assetPacks, Unity.Entities.Entity asset) : System.Collections.Generic.List<Unity.Entities.Entity>`  
- `private FilterThemesByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> themes, Unity.Entities.Entity asset) : System.Collections.Generic.List<Unity.Entities.Entity>`  
- `private GetClosestAssetInPacks(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs) : Unity.Entities.Entity`  
- `private GetClosestAssetInThemes(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes) : Unity.Entities.Entity`  
- `private GetFirstItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs) : Unity.Entities.Entity`  
- `private GetFirstPack(Unity.Entities.Entity assetEntity) : Unity.Entities.Entity`  
- `private GetFirstTheme(Unity.Entities.Entity assetEntity) : Unity.Entities.Entity`  
- `private GetFirstUnlockedItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs) : Unity.Entities.Entity`  
- `private GetSortedCategories(Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  
- `private GetSortedToolbarGroups() : Unity.Collections.NativeArray<Game.UI.UIObjectInfo>`  
- `private IsMatchingAssetCategory(Unity.Entities.Entity assetEntity, Unity.Entities.Entity assetCategoryEntity) : System.Boolean`  
- `private IsMatchingPack(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs) : System.Boolean`  
- `private IsMatchingTheme(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private SelectAsset(Unity.Entities.Entity assetEntity, System.Boolean updateTool) : System.Void`  
- `private SelectAssetCategory(Unity.Entities.Entity assetCategory) : System.Void`  
- `private SelectAssetMenu(Unity.Entities.Entity assetMenu) : System.Void`  
- `private SetAgeMask(System.Int32 ageMask) : System.Void`  
- `private SetSelectedAssetPacks(System.Collections.Generic.List<Unity.Entities.Entity> packs) : System.Void`  
- `private SetSelectedThemes(System.Collections.Generic.List<Unity.Entities.Entity> themes) : System.Void`  
- `private ToggleToolOptions(System.Boolean enabled) : System.Void`  
- `private UpdateHighlights(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity) : System.Void`  

## Nested types

- `Game.UI.InGame.ToolbarUISystem+ToolbarItemType`  

