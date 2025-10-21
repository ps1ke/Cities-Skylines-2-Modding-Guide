# Game.UI.InGame.ToolbarUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolbarUISystem : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.UI.InGame.UpgradeMenuUISystem m_UpgradeMenuUISystem;
    private Game.UI.InGame.ActionsSection m_ActionsSection;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    private Unity.Entities.EntityQuery m_AssetPackQuery;
    private Unity.Entities.EntityQuery m_ToolbarGroupQuery;
    private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
    private Colossal.UI.Binding.RawValueBinding m_ToolbarGroupsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetMenuCategoriesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetsBinding;
    private Colossal.UI.Binding.RawValueBinding m_ThemesBinding;
    private Colossal.UI.Binding.RawValueBinding m_AssetPacksBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_AgeMaskBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedThemesBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedAssetPacksBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetMenuBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetCategoryBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetBinding;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedCategories;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedAssets;
    private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedThemes;
    private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedAssetPacks;
    private System.Boolean m_UniqueAssetStatusChanged;
    private System.Boolean m_HasUnlockedPrefabLastFrame;
    private static const System.String kGroup;

    public System.Boolean hasActiveSelection { get; }

    public ToolbarUISystem();

    private System.Collections.Generic.List<Unity.Entities.Entity> <OnCreate>b__34_0();
    private System.Collections.Generic.List<Unity.Entities.Entity> <OnCreate>b__34_1();
    private System.Void ActivatePrefabTool(Unity.Entities.Entity assetEntity);
    private System.Void Apply(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity, System.Boolean updateTool);
    public System.Void BindAsset(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed);
    private System.Void BindAssetCategories(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetMenu);
    private System.Void BindAssets(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetCategory);
    private System.Void BindPacks(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindThemes(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindToolbarGroups(Colossal.UI.Binding.IJsonWriter writer);
    public System.Void ClearAssetSelection();
    private System.Void ClearAssetSelection(System.Boolean updateTool);
    private System.Void FilterByPack(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity packEntity);
    private System.Void FilterByPacks(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> packs);
    private System.Void FilterByTheme(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity themeEntity);
    private System.Void FilterByThemes(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> themes);
    private System.Void FilterOutUpgrades(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos);
    private System.Collections.Generic.List<Unity.Entities.Entity> FilterPacksByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> assetPacks, Unity.Entities.Entity asset);
    private System.Collections.Generic.List<Unity.Entities.Entity> FilterThemesByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> themes, Unity.Entities.Entity asset);
    private Unity.Entities.Entity GetClosestAssetInPacks(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs);
    private Unity.Entities.Entity GetClosestAssetInThemes(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes);
    private Unity.Entities.Entity GetFirstItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs);
    private Unity.Entities.Entity GetFirstPack(Unity.Entities.Entity assetEntity);
    private Unity.Entities.Entity GetFirstTheme(Unity.Entities.Entity assetEntity);
    private Unity.Entities.Entity GetFirstUnlockedItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs);
    private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedCategories(Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements);
    private Unity.Collections.NativeArray<Game.UI.UIObjectInfo> GetSortedToolbarGroups();
    private System.Boolean IsMatchingAssetCategory(Unity.Entities.Entity assetEntity, Unity.Entities.Entity assetCategoryEntity);
    private System.Boolean IsMatchingPack(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs);
    private System.Boolean IsMatchingTheme(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void SelectAsset(Unity.Entities.Entity assetEntity, System.Boolean updateTool);
    private System.Void SelectAssetCategory(Unity.Entities.Entity assetCategory);
    private System.Void SelectAssetMenu(Unity.Entities.Entity assetMenu);
    private System.Void SetAgeMask(System.Int32 ageMask);
    private System.Void SetSelectedAssetPacks(System.Collections.Generic.List<Unity.Entities.Entity> packs);
    private System.Void SetSelectedThemes(System.Collections.Generic.List<Unity.Entities.Entity> themes);
    private System.Void ToggleToolOptions(System.Boolean enabled);
    private System.Void UpdateHighlights(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  

```csharp
private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.UI.InGame.UpgradeMenuUISystem m_UpgradeMenuUISystem`  

```csharp
private Game.UI.InGame.UpgradeMenuUISystem m_UpgradeMenuUISystem;
```

- `private Game.UI.InGame.ActionsSection m_ActionsSection`  

```csharp
private Game.UI.InGame.ActionsSection m_ActionsSection;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `private Unity.Entities.EntityQuery m_AssetPackQuery`  

```csharp
private Unity.Entities.EntityQuery m_AssetPackQuery;
```

- `private Unity.Entities.EntityQuery m_ToolbarGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_ToolbarGroupQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedPrefabQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_ToolbarGroupsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ToolbarGroupsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetMenuCategoriesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetMenuCategoriesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AssetsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ThemesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ThemesBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_AssetPacksBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_AssetPacksBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_AgeMaskBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_AgeMaskBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedThemesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedThemesBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedAssetPacksBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_SelectedAssetPacksBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetMenuBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetMenuBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetCategoryBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetCategoryBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedAssetBinding;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedCategories`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedCategories;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedAssets`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Unity.Entities.Entity> m_LastSelectedAssets;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedThemes`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedThemes;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedAssetPacks`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> m_SelectedAssetPacks;
```

- `private System.Boolean m_UniqueAssetStatusChanged`  

```csharp
private System.Boolean m_UniqueAssetStatusChanged;
```

- `private System.Boolean m_HasUnlockedPrefabLastFrame`  

```csharp
private System.Boolean m_HasUnlockedPrefabLastFrame;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public System.Boolean hasActiveSelection { get }`  

```csharp
public System.Boolean hasActiveSelection { get; }
```


## Constructors

- `public ToolbarUISystem()`  

```csharp
public ToolbarUISystem();
```


## Methods

- `private <OnCreate>b__34_0() : System.Collections.Generic.List<Unity.Entities.Entity>`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> <OnCreate>b__34_0();
```

- `private <OnCreate>b__34_1() : System.Collections.Generic.List<Unity.Entities.Entity>`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> <OnCreate>b__34_1();
```

- `private ActivatePrefabTool(Unity.Entities.Entity assetEntity) : System.Void`  

```csharp
private System.Void ActivatePrefabTool(Unity.Entities.Entity assetEntity);
```

- `private Apply(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity, System.Boolean updateTool = False) : System.Void`  

```csharp
private System.Void Apply(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity, System.Boolean updateTool);
```

- `public BindAsset(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique = False, System.Boolean placed = False) : System.Void`  

```csharp
public System.Void BindAsset(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity, System.Boolean unique, System.Boolean placed);
```

- `private BindAssetCategories(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetMenu) : System.Void`  

```csharp
private System.Void BindAssetCategories(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetMenu);
```

- `private BindAssets(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetCategory) : System.Void`  

```csharp
private System.Void BindAssets(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity assetCategory);
```

- `private BindPacks(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindPacks(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindThemes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindThemes(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindToolbarGroups(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindToolbarGroups(Colossal.UI.Binding.IJsonWriter writer);
```

- `public ClearAssetSelection() : System.Void`  

```csharp
public System.Void ClearAssetSelection();
```

- `private ClearAssetSelection(System.Boolean updateTool) : System.Void`  

```csharp
private System.Void ClearAssetSelection(System.Boolean updateTool);
```

- `private FilterByPack(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity packEntity) : System.Void`  

```csharp
private System.Void FilterByPack(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity packEntity);
```

- `private FilterByPacks(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> packs) : System.Void`  

```csharp
private System.Void FilterByPacks(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> packs);
```

- `private FilterByTheme(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity themeEntity) : System.Void`  

```csharp
private System.Void FilterByTheme(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, Unity.Entities.Entity themeEntity);
```

- `private FilterByThemes(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> themes) : System.Void`  

```csharp
private System.Void FilterByThemes(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos, System.Collections.Generic.List<Unity.Entities.Entity> themes);
```

- `private FilterOutUpgrades(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos) : System.Void`  

```csharp
private System.Void FilterOutUpgrades(Unity.Collections.NativeList<Game.UI.UIObjectInfo> elementInfos);
```

- `private FilterPacksByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> assetPacks, Unity.Entities.Entity asset) : System.Collections.Generic.List<Unity.Entities.Entity>`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> FilterPacksByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> assetPacks, Unity.Entities.Entity asset);
```

- `private FilterThemesByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> themes, Unity.Entities.Entity asset) : System.Collections.Generic.List<Unity.Entities.Entity>`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> FilterThemesByAsset(Unity.Collections.NativeList<Game.UI.UIObjectInfo> themes, Unity.Entities.Entity asset);
```

- `private GetClosestAssetInPacks(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetClosestAssetInPacks(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs);
```

- `private GetClosestAssetInThemes(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetClosestAssetInThemes(Unity.Entities.Entity oldAssetEntity, Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes);
```

- `private GetFirstItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetFirstItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs);
```

- `private GetFirstPack(Unity.Entities.Entity assetEntity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetFirstPack(Unity.Entities.Entity assetEntity);
```

- `private GetFirstTheme(Unity.Entities.Entity assetEntity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetFirstTheme(Unity.Entities.Entity assetEntity);
```

- `private GetFirstUnlockedItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetFirstUnlockedItem(Unity.Entities.Entity groupEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs);
```

- `private GetSortedCategories(Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements) : Unity.Collections.NativeList<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeList<Game.UI.UIObjectInfo> GetSortedCategories(Unity.Entities.DynamicBuffer<Game.Prefabs.UIGroupElement> elements);
```

- `private GetSortedToolbarGroups() : Unity.Collections.NativeArray<Game.UI.UIObjectInfo>`  

```csharp
private Unity.Collections.NativeArray<Game.UI.UIObjectInfo> GetSortedToolbarGroups();
```

- `private IsMatchingAssetCategory(Unity.Entities.Entity assetEntity, Unity.Entities.Entity assetCategoryEntity) : System.Boolean`  

```csharp
private System.Boolean IsMatchingAssetCategory(Unity.Entities.Entity assetEntity, Unity.Entities.Entity assetCategoryEntity);
```

- `private IsMatchingPack(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs) : System.Boolean`  

```csharp
private System.Boolean IsMatchingPack(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> packs);
```

- `private IsMatchingTheme(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes) : System.Boolean`  

```csharp
private System.Boolean IsMatchingTheme(Unity.Entities.Entity assetEntity, System.Collections.Generic.List<Unity.Entities.Entity> themes);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed) : System.Void`  

```csharp
private System.Void OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private SelectAsset(Unity.Entities.Entity assetEntity, System.Boolean updateTool) : System.Void`  

```csharp
private System.Void SelectAsset(Unity.Entities.Entity assetEntity, System.Boolean updateTool);
```

- `private SelectAssetCategory(Unity.Entities.Entity assetCategory) : System.Void`  

```csharp
private System.Void SelectAssetCategory(Unity.Entities.Entity assetCategory);
```

- `private SelectAssetMenu(Unity.Entities.Entity assetMenu) : System.Void`  

```csharp
private System.Void SelectAssetMenu(Unity.Entities.Entity assetMenu);
```

- `private SetAgeMask(System.Int32 ageMask) : System.Void`  

```csharp
private System.Void SetAgeMask(System.Int32 ageMask);
```

- `private SetSelectedAssetPacks(System.Collections.Generic.List<Unity.Entities.Entity> packs) : System.Void`  

```csharp
private System.Void SetSelectedAssetPacks(System.Collections.Generic.List<Unity.Entities.Entity> packs);
```

- `private SetSelectedThemes(System.Collections.Generic.List<Unity.Entities.Entity> themes) : System.Void`  

```csharp
private System.Void SetSelectedThemes(System.Collections.Generic.List<Unity.Entities.Entity> themes);
```

- `private ToggleToolOptions(System.Boolean enabled) : System.Void`  

```csharp
private System.Void ToggleToolOptions(System.Boolean enabled);
```

- `private UpdateHighlights(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity) : System.Void`  

```csharp
private System.Void UpdateHighlights(System.Collections.Generic.List<Unity.Entities.Entity> themes, System.Collections.Generic.List<Unity.Entities.Entity> packs, Unity.Entities.Entity assetMenuEntity, Unity.Entities.Entity assetCategoryEntity, Unity.Entities.Entity assetEntity);
```


## Nested types

- `Game.UI.InGame.ToolbarUISystem+ToolbarItemType`  

