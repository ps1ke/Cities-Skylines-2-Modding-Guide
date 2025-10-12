# Game.UI.Editor.PrefabEdítorPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.UI.Editor.EditorAssetCategorySystem m_CategorySystem`  
- `private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem`  
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedPrefabQuery`  
- `private Game.UI.Editor.PrefabPickerAdapter m_Adapter`  
- `private Game.UI.Editor.HierarchyMenu<Game.UI.Editor.EditorAssetCategory> m_CategoryMenu`  
- `private Game.UI.Editor.EditorAssetCategory m_AllCategory`  
- `private System.Boolean m_PrefabsDirty`  
- `private Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PrefabEdítorPanelSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GenerateCategories() : System.Void`  
- `private GetHierarchy() : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  
- `private GetPrefabTypeItems() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Item>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `private OnCreatePrefab(System.Type type) : System.Void`  
- `private OnCreatePrefabSelected() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdatePrefabs() : System.Void`  

## Nested types

- `Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle`  
- `Game.UI.Editor.PrefabEdítorPanelSystem+<GetHierarchy>d__17`  
- `Game.UI.Editor.PrefabEdítorPanelSystem+<GetPrefabTypeItems>d__20`  

