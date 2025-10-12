# Game.UI.Editor.EditorAssetCategorySystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_ServiceQuery`  
- `private Unity.Entities.EntityQuery m_ZoneQuery`  
- `private Unity.Entities.EntityQuery m_ThemeQuery`  
- `private Unity.Entities.EntityQuery m_Overrides`  
- `private Unity.Entities.EntityQuery m_PrefabModificationQuery`  
- `private System.Boolean m_Dirty`  
- `private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle`  

## Constructors

- `public EditorAssetCategorySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private AddCategory(Game.UI.Editor.EditorAssetCategory category, Game.UI.Editor.EditorAssetCategory parent = null) : System.Void`  
- `private AddOverrides() : System.Void`  
- `private ClearCategories() : System.Void`  
- `private CreateCategory(System.String path) : Game.UI.Editor.EditorAssetCategory`  
- `private GenerateAreaCategories() : System.Void`  
- `private GenerateBridgeCategory() : System.Void`  
- `private GenerateBuildingCategories() : System.Void`  
- `private GenerateBushCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateCategories() : System.Void`  
- `private GenerateCharacterCategories() : System.Void`  
- `private GenerateEffectCategories() : System.Void`  
- `private GenerateFoliageCategories() : System.Void`  
- `private GenerateIndustrialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateLocationCategories() : System.Void`  
- `private GenerateMiscBuildingCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GeneratePropCategories() : System.Void`  
- `private GeneratePublicTransportVehicleCategory(Game.Prefabs.TransportType transportType, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateResidentialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateRoadCategory() : System.Void`  
- `private GenerateServiceBuildingCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateServiceVehicleCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateSpawnableBuildingCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateSurfaceCategories() : System.Void`  
- `private GenerateTrackCategories() : System.Void`  
- `private GenerateTrackTypeCategory(Game.Net.TrackTypes trackTypes, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateTreeCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `private GenerateVehicleCategories() : System.Void`  
- `private GenerateZoneCategories(Game.Zones.AreaType areaType, System.Boolean office, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  
- `public GetCategories(System.Boolean ignoreEmpty = True) : System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory>`  
- `private GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty) : System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>>`  
- `public GetHierarchy(System.Boolean ignoreEmpty = True) : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+ServiceTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+ZoneTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+PublicTransportTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+MaintenanceTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+ThemeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+TrackTypeFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+SignatureBuildingFilter`  
- `Game.UI.Editor.EditorAssetCategorySystem+TypeHandle`  
- `Game.UI.Editor.EditorAssetCategorySystem+<GetCategories>d__11`  
- `Game.UI.Editor.EditorAssetCategorySystem+<GetCategoriesImpl>d__15`  
- `Game.UI.Editor.EditorAssetCategorySystem+<GetHierarchy>d__12`  
- `Game.UI.Editor.EditorAssetCategorySystem+<__GetCategoriesImpl_17B9CE12>d__51`  

