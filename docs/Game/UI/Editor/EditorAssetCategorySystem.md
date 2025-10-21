# Game.UI.Editor.EditorAssetCategorySystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorAssetCategorySystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Unity.Entities.EntityQuery m_ZoneQuery;
    private Unity.Entities.EntityQuery m_ThemeQuery;
    private Unity.Entities.EntityQuery m_Overrides;
    private Unity.Entities.EntityQuery m_PrefabModificationQuery;
    private System.Boolean m_Dirty;
    private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle;

    public EditorAssetCategorySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddCategory(Game.UI.Editor.EditorAssetCategory category, Game.UI.Editor.EditorAssetCategory parent);
    private System.Void AddOverrides();
    private System.Void ClearCategories();
    private Game.UI.Editor.EditorAssetCategory CreateCategory(System.String path);
    private System.Void GenerateAreaCategories();
    private System.Void GenerateBridgeCategory();
    private System.Void GenerateBuildingCategories();
    private System.Void GenerateBushCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateCategories();
    private System.Void GenerateCharacterCategories();
    private System.Void GenerateEffectCategories();
    private System.Void GenerateFoliageCategories();
    private System.Void GenerateIndustrialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateLocationCategories();
    private System.Void GenerateMiscBuildingCategory(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GeneratePropCategories();
    private System.Void GeneratePublicTransportVehicleCategory(Game.Prefabs.TransportType transportType, Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateResidentialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateRoadCategory();
    private System.Void GenerateServiceBuildingCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateServiceVehicleCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateSpawnableBuildingCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateSurfaceCategories();
    private System.Void GenerateTrackCategories();
    private System.Void GenerateTrackTypeCategory(Game.Net.TrackTypes trackTypes, Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateTreeCategories(Game.UI.Editor.EditorAssetCategory parent);
    private System.Void GenerateVehicleCategories();
    private System.Void GenerateZoneCategories(Game.Zones.AreaType areaType, System.Boolean office, Game.UI.Editor.EditorAssetCategory parent);
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> GetCategories(System.Boolean ignoreEmpty);
    private System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>> GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty);
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>> GetHierarchy(System.Boolean ignoreEmpty);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_Categories;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.Editor.EditorAssetCategory> m_PathMap;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Unity.Entities.EntityQuery m_ZoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ZoneQuery;
```

- `private Unity.Entities.EntityQuery m_ThemeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ThemeQuery;
```

- `private Unity.Entities.EntityQuery m_Overrides`  

```csharp
private Unity.Entities.EntityQuery m_Overrides;
```

- `private Unity.Entities.EntityQuery m_PrefabModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabModificationQuery;
```

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.EditorAssetCategorySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EditorAssetCategorySystem()`  

```csharp
public EditorAssetCategorySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddCategory(Game.UI.Editor.EditorAssetCategory category, Game.UI.Editor.EditorAssetCategory parent = null) : System.Void`  

```csharp
private System.Void AddCategory(Game.UI.Editor.EditorAssetCategory category, Game.UI.Editor.EditorAssetCategory parent);
```

- `private AddOverrides() : System.Void`  

```csharp
private System.Void AddOverrides();
```

- `private ClearCategories() : System.Void`  

```csharp
private System.Void ClearCategories();
```

- `private CreateCategory(System.String path) : Game.UI.Editor.EditorAssetCategory`  

```csharp
private Game.UI.Editor.EditorAssetCategory CreateCategory(System.String path);
```

- `private GenerateAreaCategories() : System.Void`  

```csharp
private System.Void GenerateAreaCategories();
```

- `private GenerateBridgeCategory() : System.Void`  

```csharp
private System.Void GenerateBridgeCategory();
```

- `private GenerateBuildingCategories() : System.Void`  

```csharp
private System.Void GenerateBuildingCategories();
```

- `private GenerateBushCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateBushCategories(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateCategories() : System.Void`  

```csharp
private System.Void GenerateCategories();
```

- `private GenerateCharacterCategories() : System.Void`  

```csharp
private System.Void GenerateCharacterCategories();
```

- `private GenerateEffectCategories() : System.Void`  

```csharp
private System.Void GenerateEffectCategories();
```

- `private GenerateFoliageCategories() : System.Void`  

```csharp
private System.Void GenerateFoliageCategories();
```

- `private GenerateIndustrialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateIndustrialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateLocationCategories() : System.Void`  

```csharp
private System.Void GenerateLocationCategories();
```

- `private GenerateMiscBuildingCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateMiscBuildingCategory(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GeneratePropCategories() : System.Void`  

```csharp
private System.Void GeneratePropCategories();
```

- `private GeneratePublicTransportVehicleCategory(Game.Prefabs.TransportType transportType, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GeneratePublicTransportVehicleCategory(Game.Prefabs.TransportType transportType, Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateResidentialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateResidentialVehicleCategory(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateRoadCategory() : System.Void`  

```csharp
private System.Void GenerateRoadCategory();
```

- `private GenerateServiceBuildingCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateServiceBuildingCategories(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateServiceVehicleCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateServiceVehicleCategories(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateSpawnableBuildingCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateSpawnableBuildingCategories(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateSurfaceCategories() : System.Void`  

```csharp
private System.Void GenerateSurfaceCategories();
```

- `private GenerateTrackCategories() : System.Void`  

```csharp
private System.Void GenerateTrackCategories();
```

- `private GenerateTrackTypeCategory(Game.Net.TrackTypes trackTypes, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateTrackTypeCategory(Game.Net.TrackTypes trackTypes, Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateTreeCategories(Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateTreeCategories(Game.UI.Editor.EditorAssetCategory parent);
```

- `private GenerateVehicleCategories() : System.Void`  

```csharp
private System.Void GenerateVehicleCategories();
```

- `private GenerateZoneCategories(Game.Zones.AreaType areaType, System.Boolean office, Game.UI.Editor.EditorAssetCategory parent) : System.Void`  

```csharp
private System.Void GenerateZoneCategories(Game.Zones.AreaType areaType, System.Boolean office, Game.UI.Editor.EditorAssetCategory parent);
```

- `public GetCategories(System.Boolean ignoreEmpty = True) : System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory>`  

```csharp
public System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> GetCategories(System.Boolean ignoreEmpty);
```

- `private GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty) : System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>>`  

```csharp
private System.Collections.Generic.IEnumerable<System.ValueTuple<Game.UI.Editor.EditorAssetCategory, System.Int32>> GetCategoriesImpl(System.Collections.Generic.IEnumerable<Game.UI.Editor.EditorAssetCategory> categories, System.Int32 level, System.Boolean ignoreEmpty);
```

- `public GetHierarchy(System.Boolean ignoreEmpty = True) : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  

```csharp
public System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>> GetHierarchy(System.Boolean ignoreEmpty);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


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

