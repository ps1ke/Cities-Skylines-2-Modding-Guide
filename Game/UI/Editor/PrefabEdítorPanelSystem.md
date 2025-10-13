# Game.UI.Editor.PrefabEdítorPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabEdítorPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.Editor.EditorAssetCategorySystem m_CategorySystem;
    private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_ModifiedPrefabQuery;
    private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
    private Game.UI.Editor.HierarchyMenu<Game.UI.Editor.EditorAssetCategory> m_CategoryMenu;
    private Game.UI.Editor.EditorAssetCategory m_AllCategory;
    private System.Boolean m_PrefabsDirty;
    private Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle __TypeHandle;

    public PrefabEdítorPanelSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void GenerateCategories();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>> GetHierarchy();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> GetPrefabTypeItems();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    private System.Void OnCreatePrefab(System.Type type);
    private System.Void OnCreatePrefabSelected();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnPrefabSelected(Game.Prefabs.PrefabBase prefab);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnUpdate();
    private System.Void UpdatePrefabs();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.Editor.EditorAssetCategorySystem m_CategorySystem`  

```csharp
private Game.UI.Editor.EditorAssetCategorySystem m_CategorySystem;
```

- `private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem`  

```csharp
private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedPrefabQuery;
```

- `private Game.UI.Editor.PrefabPickerAdapter m_Adapter`  

```csharp
private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
```

- `private Game.UI.Editor.HierarchyMenu<Game.UI.Editor.EditorAssetCategory> m_CategoryMenu`  

```csharp
private Game.UI.Editor.HierarchyMenu<Game.UI.Editor.EditorAssetCategory> m_CategoryMenu;
```

- `private Game.UI.Editor.EditorAssetCategory m_AllCategory`  

```csharp
private Game.UI.Editor.EditorAssetCategory m_AllCategory;
```

- `private System.Boolean m_PrefabsDirty`  

```csharp
private System.Boolean m_PrefabsDirty;
```

- `private Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrefabEdítorPanelSystem()`  

```csharp
public PrefabEdítorPanelSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GenerateCategories() : System.Void`  

```csharp
private System.Void GenerateCategories();
```

- `private GetHierarchy() : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>> GetHierarchy();
```

- `private GetPrefabTypeItems() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Item>`  

```csharp
private System.Collections.Generic.IEnumerable<Game.UI.Editor.Item> GetPrefabTypeItems();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `private OnCreatePrefab(System.Type type) : System.Void`  

```csharp
private System.Void OnCreatePrefab(System.Type type);
```

- `private OnCreatePrefabSelected() : System.Void`  

```csharp
private System.Void OnCreatePrefabSelected();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void OnPrefabSelected(Game.Prefabs.PrefabBase prefab);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private UpdatePrefabs() : System.Void`  

```csharp
private System.Void UpdatePrefabs();
```


## Nested types

- `Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle`  
- `Game.UI.Editor.PrefabEdítorPanelSystem+<GetHierarchy>d__17`  
- `Game.UI.Editor.PrefabEdítorPanelSystem+<GetPrefabTypeItems>d__20`  

