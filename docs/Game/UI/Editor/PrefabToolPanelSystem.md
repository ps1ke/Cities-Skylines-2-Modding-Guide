# Game.UI.Editor.PrefabToolPanelSystem

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
- `private Unity.Entities.EntityQuery m_PrefabQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedPrefabQuery`  
- `private Game.UI.Editor.PrefabPickerAdapter m_Adapter`  
- `private Game.UI.Editor.HierarchyMenu<Game.UI.Editor.EditorAssetCategory> m_CategoryMenu`  
- `private Game.UI.Editor.EditorAssetCategory m_AllCategory`  
- `private Game.UI.Editor.PrefabToolPanelSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PrefabToolPanelSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GenerateCategories() : System.Void`  
- `private GetHierarchy() : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  
- `protected virtual OnCancel() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  
- `protected virtual OnStartRunning() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdatePrefabs() : System.Void`  

## Nested types

- `Game.UI.Editor.PrefabToolPanelSystem+TypeHandle`  
- `Game.UI.Editor.PrefabToolPanelSystem+<GetHierarchy>d__16`  

