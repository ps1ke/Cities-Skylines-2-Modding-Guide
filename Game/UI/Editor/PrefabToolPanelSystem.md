# Game.UI.Editor.PrefabToolPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrefabToolPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.Editor.EditorAssetCategorySystem m_CategorySystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_ModifiedPrefabQuery;
    private Game.UI.Editor.PrefabPickerAdapter m_Adapter;
    private Game.UI.Editor.HierarchyMenu<Game.UI.Editor.EditorAssetCategory> m_CategoryMenu;
    private Game.UI.Editor.EditorAssetCategory m_AllCategory;
    private Game.UI.Editor.PrefabToolPanelSystem+TypeHandle __TypeHandle;

    public PrefabToolPanelSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void GenerateCategories();
    private System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>> GetHierarchy();
    protected virtual System.Boolean OnCancel();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
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

- `private Game.UI.Editor.PrefabToolPanelSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.PrefabToolPanelSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrefabToolPanelSystem()`  

```csharp
public PrefabToolPanelSystem();
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

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected virtual System.Boolean OnCancel();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
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

- `Game.UI.Editor.PrefabToolPanelSystem+TypeHandle`  
- `Game.UI.Editor.PrefabToolPanelSystem+<GetHierarchy>d__16`  

