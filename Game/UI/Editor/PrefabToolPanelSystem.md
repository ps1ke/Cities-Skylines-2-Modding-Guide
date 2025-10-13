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
[Preserve]
	public PrefabToolPanelSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private GenerateCategories() : System.Void`  

```csharp
private void GenerateCategories()
	{
		m_AllCategory = new EditorAssetCategory
		{
			id = "All",
			path = "All",
			entityQuery = GetEntityQuery(new EntityQueryDesc
			{
				All = new ComponentType[1] { ComponentType.ReadOnly<PrefabData>() },
				Any = new ComponentType[6]
				{
					ComponentType.ReadOnly<ObjectData>(),
					ComponentType.ReadOnly<EffectData>(),
					ComponentType.ReadOnly<ActivityLocationData>(),
					ComponentType.ReadOnly<NetData>(),
					ComponentType.ReadOnly<NetLaneData>(),
					ComponentType.ReadOnly<AreaData>()
				},
				None = new ComponentType[4]
				{
					ComponentType.ReadOnly<BrandObjectData>(),
					ComponentType.ReadOnly<CarLaneData>(),
					ComponentType.ReadOnly<TrackLaneData>(),
					ComponentType.ReadOnly<ConnectionLaneData>()
				}
			}),
			defaultSelection = true,
			includeChildCategories = false
		};
	}
```

- `private GetHierarchy() : System.Collections.Generic.IEnumerable<Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>>`  

```csharp
private IEnumerable<HierarchyItem<EditorAssetCategory>> GetHierarchy()
	{
		yield return m_AllCategory.ToHierarchyItem();
		foreach (HierarchyItem<EditorAssetCategory> item in m_CategorySystem.GetHierarchy())
		{
			yield return item;
		}
	}
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected override bool OnCancel()
	{
		if (m_Adapter.selectedPrefab != null)
		{
			m_Adapter.selectedPrefab = null;
			m_ToolSystem.ActivatePrefabTool(null);
			return false;
		}
		return base.OnCancel();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CategorySystem = base.World.GetOrCreateSystemManaged<EditorAssetCategorySystem>();
		m_ModifiedPrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabData>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			}
		});
		m_Adapter = new PrefabPickerAdapter();
		PrefabPickerAdapter prefabPickerAdapter = m_Adapter;
		prefabPickerAdapter.EventPrefabSelected = (Action<PrefabBase>)Delegate.Combine(prefabPickerAdapter.EventPrefabSelected, new Action<PrefabBase>(OnPrefabSelected));
		title = "Editor.TOOL[PrefabTool]";
		IWidget[] obj = new IWidget[4]
		{
			new PopupSearchField
			{
				adapter = m_Adapter
			},
			new FilterMenu
			{
				adapter = m_Adapter
			},
			null,
			null
		};
		Row row = new Row
		{
			flex = FlexLayout.Fill
		};
		IWidget[] array = new IWidget[2];
		HierarchyMenu<EditorAssetCategory> obj2 = new HierarchyMenu<EditorAssetCategory>
		{
			selectionType = HierarchyMenu.SelectionType.singleSelection,
			onSelectionChange = UpdatePrefabs,
			flex = new FlexLayout(1f, 0f, 0),
			path = "PrefabToolCategories"
		};
		HierarchyMenu<EditorAssetCategory> hierarchyMenu = obj2;
		m_CategoryMenu = obj2;
		array[0] = hierarchyMenu;
		array[1] = new ItemPicker<PrefabItem>
		{
			adapter = m_Adapter,
			hasFavorites = true,
			flex = new FlexLayout(2f, 0f, 0),
			selectOnFocus = true
		};
		row.children = array;
		obj[2] = row;
		obj[3] = new ItemPickerFooter
		{
			adapter = m_Adapter
		};
		children = obj;
		GenerateCategories();
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		m_Adapter.searchQuery = string.Empty;
		m_Adapter.selectedPrefab = null;
	}
```

- `private OnPrefabSelected(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void OnPrefabSelected(PrefabBase prefab)
	{
		m_ToolSystem.ActivatePrefabTool(m_Adapter.selectedPrefab);
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_Adapter.LoadSettings();
		m_CategoryMenu.items = GetHierarchy();
		UpdatePrefabs();
		m_ToolSystem.ActivatePrefabTool(m_Adapter.selectedPrefab);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (!m_ModifiedPrefabQuery.IsEmptyIgnoreFilter)
		{
			UpdatePrefabs();
		}
		m_Adapter.Update();
		m_Adapter.selectedPrefab = m_ToolSystem.activePrefab;
	}
```

- `private UpdatePrefabs() : System.Void`  

```csharp
private void UpdatePrefabs()
	{
		if (m_CategoryMenu.GetSelectedItem(out var selection))
		{
			HashSet<PrefabBase> prefabs = selection.GetPrefabs(base.EntityManager, m_PrefabSystem, InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef));
			m_Adapter.SetPrefabs(prefabs);
		}
	}
```


## Nested types

- `Game.UI.Editor.PrefabToolPanelSystem+TypeHandle`  
- `Game.UI.Editor.PrefabToolPanelSystem+<GetHierarchy>d__16`  

