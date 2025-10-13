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
[Preserve]
	public PrefabEdítorPanelSystem()
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
				None = new ComponentType[1] { ComponentType.ReadOnly<MeshData>() }
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

- `private GetPrefabTypeItems() : System.Collections.Generic.IEnumerable<Game.UI.Editor.Item>`  

```csharp
private IEnumerable<Item> GetPrefabTypeItems()
	{
		foreach (Type item in TypePickerPanel.GetAllConcreteTypesDerivedFrom<PrefabBase>())
		{
			ComponentMenu customAttribute = item.GetCustomAttribute<ComponentMenu>();
			yield return new Item
			{
				type = item,
				name = WidgetReflectionUtils.NicifyVariableName(item.Name),
				parentDir = customAttribute?.menu
			};
		}
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
		m_InspectorPanelSystem = base.World.GetOrCreateSystemManaged<InspectorPanelSystem>();
		m_ModifiedPrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabData>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_Adapter = new PrefabPickerAdapter
		{
			displayPrefabTypeTooltip = true
		};
		PrefabPickerAdapter prefabPickerAdapter = m_Adapter;
		prefabPickerAdapter.EventPrefabSelected = (Action<PrefabBase>)Delegate.Combine(prefabPickerAdapter.EventPrefabSelected, new Action<PrefabBase>(OnPrefabSelected));
		title = "Editor.TOOL[PrefabEditorTool]";
		IWidget[] obj = new IWidget[5]
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
			path = "PrefabEditorToolCategories"
		};
		HierarchyMenu<EditorAssetCategory> hierarchyMenu = obj2;
		m_CategoryMenu = obj2;
		array[0] = hierarchyMenu;
		array[1] = new ItemPicker<PrefabItem>
		{
			adapter = m_Adapter,
			hasFavorites = true,
			flex = new FlexLayout(2f, 0f, 0)
		};
		row.children = array;
		obj[2] = row;
		obj[3] = new ItemPickerFooter
		{
			adapter = m_Adapter
		};
		obj[4] = new Button
		{
			displayName = "Editor.CREATE_NEW_PREFAB",
			action = OnCreatePrefabSelected
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

- `private OnCreatePrefab(System.Type type) : System.Void`  

```csharp
private void OnCreatePrefab(Type type)
	{
		CloseSubPanel();
		PrefabBase prefabBase = (PrefabBase)ScriptableObject.CreateInstance(type);
		prefabBase.name = type.Name;
		m_PrefabSystem.AddPrefab(prefabBase);
		OnPrefabSelected(prefabBase);
	}
```

- `private OnCreatePrefabSelected() : System.Void`  

```csharp
private void OnCreatePrefabSelected()
	{
		base.activeSubPanel = new TypePickerPanel("Editor.CREATE_NEW_PREFAB", "Editor.PREFAB_TYPES", GetPrefabTypeItems().ToList(), OnCreatePrefab, base.CloseSubPanel);
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
		m_InspectorPanelSystem.SelectPrefab(prefab);
		base.activeSubPanel = m_InspectorPanelSystem;
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
			m_PrefabsDirty = true;
		}
		if (m_PrefabsDirty && base.activeSubPanel == null)
		{
			UpdatePrefabs();
		}
		m_Adapter.Update();
	}
```

- `private UpdatePrefabs() : System.Void`  

```csharp
private void UpdatePrefabs()
	{
		m_PrefabsDirty = false;
		if (m_CategoryMenu.GetSelectedItem(out var selection))
		{
			HashSet<PrefabBase> prefabs = selection.GetPrefabs(base.EntityManager, m_PrefabSystem, InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef));
			m_Adapter.SetPrefabs(prefabs);
		}
	}
```


## Nested types

- `Game.UI.Editor.PrefabEdítorPanelSystem+TypeHandle`  
- `Game.UI.Editor.PrefabEdítorPanelSystem+<GetHierarchy>d__17`  
- `Game.UI.Editor.PrefabEdítorPanelSystem+<GetPrefabTypeItems>d__20`  

