# Game.UI.Editor.EditorHierarchyUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EditorHierarchyUISystem : Game.UI.UISystemBase
{
    public System.Action<Unity.Entities.Entity> onSave;
    public System.Action<Unity.Entities.Entity> onBulldoze;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem;
    private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Unity.Entities.EntityQuery m_ObjectQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding;
    private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy;
    private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds;
    private System.Int32 m_TotalCount;
    private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId;
    private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport;
    private System.Int32 m_NextViewportStartIndex;
    private System.Int32 m_NextViewportEndIndex;
    private System.Boolean m_Dirty;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode;
    private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set; }

    public EditorHierarchyUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 <OnCreate>b__27_0();
    private Game.UI.Editor.EditorHierarchyUISystem+ItemId <OnCreate>b__27_1();
    private Game.UI.Editor.EditorHierarchyUISystem+Viewport <OnCreate>b__27_2();
    private System.Void <OnCreate>b__27_3(System.Int32 mode);
    private System.Boolean <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
    private System.Boolean <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
    private Game.UI.Editor.EditorHierarchyUISystem+ViewportItem BuildViewportItem(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem item);
    private Unity.Jobs.JobHandle EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy, Unity.Jobs.JobHandle __inputDependency);
    private Game.UI.Localization.LocalizedString GetName(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
    private Game.UI.Localization.LocalizedString GetTooltip(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
    private System.Int32 GetWidth();
    private System.Void OnBulldoze(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnSave(Unity.Entities.Entity entity);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnUpdate();
    private System.Void RefreshCameraController(Game.UI.Editor.EditorHierarchyUISystem+CameraMode mode);
    private System.Void SetExpanded(Game.UI.Editor.EditorHierarchyUISystem+ItemId id, System.Boolean expanded);
    public System.Void SetSelectedId(Game.UI.Editor.EditorHierarchyUISystem+ItemId id);
    private System.Void SetViewportRange(System.Int32 startIndex, System.Int32 endIndex);
    private System.Void SetWidth(System.Int32 width);
    private System.Void ToggleCameraMode(Game.UI.Editor.EditorHierarchyUISystem+CameraMode cameraMode);
    private System.Void UpdateHierarchy(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy);
    private System.Void UpdateSelection();
    private System.Void UpdateViewport(System.Boolean force);
    private System.Boolean ViewportChanged();
}
```


## Fields

- `public System.Action<Unity.Entities.Entity> onSave`  

```csharp
public System.Action<Unity.Entities.Entity> onSave;
```

- `public System.Action<Unity.Entities.Entity> onBulldoze`  

```csharp
public System.Action<Unity.Entities.Entity> onBulldoze;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem`  

```csharp
private Game.UI.Editor.EditorToolUISystem m_EditorToolUISystem;
```

- `private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  

```csharp
private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Unity.Entities.EntityQuery m_ObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.EditorHierarchyUISystem+Viewport> m_ViewportBinding;
```

- `private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> <panelItems>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy`  

```csharp
private Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy;
```

- `private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds`  

```csharp
private Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds;
```

- `private System.Int32 m_TotalCount`  

```csharp
private System.Int32 m_TotalCount;
```

- `private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+ItemId m_SelectedId;
```

- `private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+Viewport m_Viewport;
```

- `private System.Int32 m_NextViewportStartIndex`  

```csharp
private System.Int32 m_NextViewportStartIndex;
```

- `private System.Int32 m_NextViewportEndIndex`  

```csharp
private System.Int32 m_NextViewportEndIndex;
```

- `private System.Boolean m_Dirty`  

```csharp
private System.Boolean m_Dirty;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_CameraMode;
```

- `private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.Editor.EditorHierarchyUISystem+PanelItem> panelItems { get; private set; }
```


## Constructors

- `public EditorHierarchyUISystem()`  

```csharp
[Preserve]
	public EditorHierarchyUISystem()
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

- `private <OnCreate>b__27_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__27_0();
```

- `private <OnCreate>b__27_1() : Game.UI.Editor.EditorHierarchyUISystem+ItemId`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+ItemId <OnCreate>b__27_1();
```

- `private <OnCreate>b__27_2() : Game.UI.Editor.EditorHierarchyUISystem+Viewport`  

```csharp
private Game.UI.Editor.EditorHierarchyUISystem+Viewport <OnCreate>b__27_2();
```

- `private <OnCreate>b__27_3(System.Int32 mode) : System.Void`  

```csharp
private System.Void <OnCreate>b__27_3(System.Int32 mode);
```

- `private <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p) : System.Boolean`  

```csharp
private System.Boolean <UpdateSelection>b__32_0(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
```

- `private <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p) : System.Boolean`  

```csharp
private System.Boolean <UpdateSelection>b__32_1(Game.UI.Editor.EditorHierarchyUISystem+PanelItem p);
```

- `private BuildViewportItem(Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem item) : Game.UI.Editor.EditorHierarchyUISystem+ViewportItem`  

```csharp
private ViewportItem BuildViewportItem(HierarchyItem item)
	{
		PrefabRef component;
		PrefabBase prefab;
		return new ViewportItem
		{
			id = item.id,
			level = item.level,
			expandable = item.expandable,
			expanded = item.expanded,
			name = GetName(item.id),
			tooltip = GetTooltip(item.id),
			selectable = item.selectable,
			saveable = (item.id.type == ItemType.Object && base.EntityManager.TryGetComponent<PrefabRef>(item.id.entity, out component) && m_PrefabSystem.TryGetPrefab<PrefabBase>(component, out prefab) && !prefab.builtin)
		};
	}
```

- `private EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy, Unity.Jobs.JobHandle __inputDependency) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(NativeList<HierarchyItem> hierarchy, JobHandle __inputDependency)
	{
		return IJobExtensions.Schedule(new EditorHierarchyUISystem_4E004959_LambdaJob_0_Job
		{
			hierarchy = hierarchy
		}, __inputDependency);
	}
```

- `private GetName(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : Game.UI.Localization.LocalizedString`  

```csharp
private LocalizedString GetName(ItemId id)
	{
		PrefabRef component2;
		DynamicBuffer<SubMesh> buffer;
		PrefabBase prefab2;
		if (id.type == ItemType.Object)
		{
			if (base.EntityManager.TryGetComponent<PrefabRef>(id.entity, out var component) && m_PrefabSystem.TryGetPrefab<PrefabBase>(component, out var prefab))
			{
				return LocalizedString.Value(prefab.name);
			}
		}
		else if (id.type == ItemType.SubMesh && base.EntityManager.TryGetComponent<PrefabRef>(id.entity, out component2) && base.EntityManager.TryGetBuffer(component2.m_Prefab, isReadOnly: true, out buffer) && id.subIndex < buffer.Length && m_PrefabSystem.TryGetPrefab<PrefabBase>(buffer[id.subIndex].m_SubMesh, out prefab2))
		{
			return LocalizedString.Value(prefab2.name);
		}
		return "Editor." + id.type.ToString().ToUpper();
	}
```

- `private GetTooltip(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : Game.UI.Localization.LocalizedString`  

```csharp
private LocalizedString GetTooltip(ItemId id)
	{
		return "Editor." + id.type.ToString().ToUpper() + "_TOOLTIP";
	}
```

- `private GetWidth() : System.Int32`  

```csharp
private int GetWidth()
	{
		return (SharedSettings.instance?.editor)?.hierarchyWidth ?? 350;
	}
```

- `private OnBulldoze(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnBulldoze(Entity entity)
	{
		onBulldoze?.Invoke(entity);
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
		m_EditorToolUISystem = base.World.GetOrCreateSystemManaged<EditorToolUISystem>();
		m_EditorPanelUISystem = base.World.GetOrCreateSystemManaged<EditorPanelUISystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_ObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		AddUpdateBinding(new GetterValueBinding<int>("editorHierarchy", "width", GetWidth));
		AddUpdateBinding(new GetterValueBinding<int>("editorHierarchy", "totalCount", () => m_TotalCount));
		AddUpdateBinding(new GetterValueBinding<ItemId>("editorHierarchy", "selectedId", () => m_SelectedId, new ValueWriter<ItemId>()));
		AddBinding(m_ViewportBinding = new GetterValueBinding<Viewport>("editorHierarchy", "viewport", () => m_Viewport, new ValueWriter<Viewport>()));
		AddBinding(m_CameraMode = new ValueBinding<int>("editorHierarchy", "cameraMode", 0));
		AddBinding(new TriggerBinding<int>("editorHierarchy", "setWidth", SetWidth));
		AddBinding(new TriggerBinding<int, int>("editorHierarchy", "setViewportRange", SetViewportRange));
		AddBinding(new TriggerBinding<ItemId>("editorHierarchy", "setSelectedId", SetSelectedId, new ValueReader<ItemId>()));
		AddBinding(new TriggerBinding<ItemId, bool>("editorHierarchy", "setExpanded", SetExpanded, new ValueReader<ItemId>()));
		AddBinding(new TriggerBinding<int>("editorHierarchy", "toggleCameraMode", delegate(int mode)
		{
			ToggleCameraMode((CameraMode)mode);
		}));
		AddBinding(new TriggerBinding<Entity>("editorHierarchy", "save", OnSave));
		AddBinding(new TriggerBinding<Entity>("editorHierarchy", "bulldoze", OnBulldoze));
		panelItems = new List<PanelItem>
		{
			new PanelItem(ItemType.Map, 0, base.World.GetOrCreateSystemManaged<MapPanelSystem>()),
			new PanelItem(ItemType.Climate, 1, base.World.GetOrCreateSystemManaged<ClimatePanelSystem>()),
			new PanelItem(ItemType.Water, 1, base.World.GetOrCreateSystemManaged<WaterPanelSystem>()),
			new PanelItem(ItemType.Resources, 1, base.World.GetOrCreateSystemManaged<ResourcePanelSystem>())
		};
		m_Hierarchy = new NativeList<HierarchyItem>(Allocator.Persistent);
		m_ExpandedIds = new NativeParallelHashSet<ItemId>(128, Allocator.Persistent);
		m_Viewport = new Viewport();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Hierarchy.Dispose();
		m_ExpandedIds.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Dirty = true;
	}
```

- `private OnSave(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnSave(Entity entity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(entity);
		EditorPrefabUtils.SavePrefab(m_PrefabSystem.GetPrefab<PrefabBase>(componentData));
		PlatformManager.instance.UnlockAchievement(Game.Achievements.Achievements.IMadeThis);
		onSave?.Invoke(entity);
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ExpandedIds.Clear();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = m_Dirty || !m_ModifiedQuery.IsEmptyIgnoreFilter;
		m_Dirty = false;
		m_TotalCount = m_Hierarchy.Length;
		UpdateSelection();
		base.OnUpdate();
		UpdateViewport(flag);
		if (flag)
		{
			UpdateHierarchy(m_Hierarchy);
		}
	}
```

- `private RefreshCameraController(Game.UI.Editor.EditorHierarchyUISystem+CameraMode mode) : System.Void`  

```csharp
private void RefreshCameraController(CameraMode mode)
	{
		if (mode == CameraMode.Default || (mode == CameraMode.Orbit && m_SelectedId.entity == Entity.Null))
		{
			if (m_CameraUpdateSystem.activeCameraController != m_CameraUpdateSystem.gamePlayController)
			{
				m_CameraUpdateSystem.gamePlayController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
				m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.gamePlayController;
			}
			return;
		}
		switch (mode)
		{
		case CameraMode.Orbit:
			m_CameraUpdateSystem.orbitCameraController.followedEntity = m_SelectedId.entity;
			if (m_CameraUpdateSystem.activeCameraController != m_CameraUpdateSystem.orbitCameraController)
			{
				m_CameraUpdateSystem.orbitCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
				m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.orbitCameraController;
			}
			break;
		case CameraMode.FirstPerson:
			if (m_CameraUpdateSystem.activeCameraController != m_CameraUpdateSystem.cinematicCameraController)
			{
				m_CameraUpdateSystem.cinematicCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
				m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.cinematicCameraController;
			}
			break;
		}
	}
```

- `private SetExpanded(Game.UI.Editor.EditorHierarchyUISystem+ItemId id, System.Boolean expanded) : System.Void`  

```csharp
private void SetExpanded(ItemId id, bool expanded)
	{
		m_Dirty = true;
		if (expanded)
		{
			m_ExpandedIds.Add(id);
		}
		else
		{
			m_ExpandedIds.Remove(id);
		}
	}
```

- `public SetSelectedId(Game.UI.Editor.EditorHierarchyUISystem+ItemId id) : System.Void`  

```csharp
public void SetSelectedId(ItemId id)
	{
		m_SelectedId = id;
		switch (id.type)
		{
		case ItemType.Object:
			m_ToolSystem.selected = id.entity;
			m_EditorToolUISystem.SelectEntity(id.entity);
			break;
		case ItemType.SubMesh:
			m_ToolSystem.selected = id.entity;
			m_EditorToolUISystem.SelectEntitySubMesh(id.entity, id.subIndex);
			break;
		default:
			m_ToolSystem.selected = Entity.Null;
			m_EditorPanelUISystem.activePanel = panelItems.FirstOrDefault((PanelItem p) => p.type == id.type)?.panel;
			break;
		}
		RefreshCameraController((CameraMode)m_CameraMode.value);
	}
```

- `private SetViewportRange(System.Int32 startIndex, System.Int32 endIndex) : System.Void`  

```csharp
private void SetViewportRange(int startIndex, int endIndex)
	{
		m_NextViewportStartIndex = startIndex;
		m_NextViewportEndIndex = endIndex;
	}
```

- `private SetWidth(System.Int32 width) : System.Void`  

```csharp
private void SetWidth(int width)
	{
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		if (editorSettings != null)
		{
			editorSettings.hierarchyWidth = width;
		}
	}
```

- `private ToggleCameraMode(Game.UI.Editor.EditorHierarchyUISystem+CameraMode cameraMode) : System.Void`  

```csharp
private void ToggleCameraMode(CameraMode cameraMode)
	{
		m_CameraMode.Update((int)cameraMode);
		RefreshCameraController(cameraMode);
	}
```

- `private UpdateHierarchy(Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> hierarchy) : System.Void`  

```csharp
private void UpdateHierarchy(NativeList<HierarchyItem> hierarchy)
	{
		hierarchy.Clear();
		foreach (PanelItem panelItem in panelItems)
		{
			hierarchy.Add(new HierarchyItem
			{
				id = new ItemId(panelItem.type),
				level = panelItem.level,
				selectable = true
			});
		}
		if (!m_ObjectQuery.IsEmptyIgnoreFilter)
		{
			ItemId itemId = new ItemId(ItemType.ObjectContainer);
			bool num = m_ExpandedIds.Contains(itemId);
			HierarchyItem value = new HierarchyItem
			{
				id = itemId,
				level = 0,
				expandable = true,
				expanded = m_ExpandedIds.Contains(itemId),
				selectable = false
			};
			hierarchy.Add(in value);
			if (num)
			{
				ObjectHierarchyJob jobData = new ObjectHierarchyJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
					m_ExpandedIds = m_ExpandedIds,
					m_Hierarchy = hierarchy
				};
				base.Dependency = JobChunkExtensions.Schedule(jobData, m_ObjectQuery, base.Dependency);
				base.Dependency = EditorHierarchyUISystem_4E004959_LambdaJob_0_Execute(hierarchy, base.Dependency);
			}
		}
	}
```

- `private UpdateSelection() : System.Void`  

```csharp
private void UpdateSelection()
	{
		if (m_EditorPanelUISystem.activePanel == null)
		{
			if (!m_SelectedId.isContainer)
			{
				m_SelectedId = default(ItemId);
			}
			return;
		}
		if (m_ToolSystem.selected != Entity.Null)
		{
			if (m_SelectedId.entity != m_ToolSystem.selected)
			{
				m_SelectedId = new ItemId
				{
					type = ItemType.Object,
					entity = m_ToolSystem.selected
				};
				RefreshCameraController((CameraMode)m_CameraMode.value);
			}
			return;
		}
		PanelItem panelItem = panelItems.FirstOrDefault((PanelItem p) => p.type == m_SelectedId.type);
		if (m_EditorPanelUISystem.activePanel != panelItem?.panel)
		{
			PanelItem panelItem2 = panelItems.FirstOrDefault((PanelItem p) => p.panel == m_EditorPanelUISystem.activePanel);
			m_SelectedId = ((panelItem2 != null) ? new ItemId(panelItem2.type) : default(ItemId));
		}
	}
```

- `private UpdateViewport(System.Boolean force) : System.Void`  

```csharp
private void UpdateViewport(bool force)
	{
		m_NextViewportStartIndex = math.clamp(m_NextViewportStartIndex, 0, m_Hierarchy.Length);
		m_NextViewportEndIndex = math.clamp(m_NextViewportEndIndex, 0, m_Hierarchy.Length);
		if (force || ViewportChanged())
		{
			m_Viewport.startIndex = m_NextViewportStartIndex;
			m_Viewport.items.Clear();
			for (int i = m_NextViewportStartIndex; i < m_NextViewportEndIndex; i++)
			{
				m_Viewport.items.Add(BuildViewportItem(m_Hierarchy[i]));
			}
			m_ViewportBinding.TriggerUpdate();
		}
	}
```

- `private ViewportChanged() : System.Boolean`  

```csharp
private bool ViewportChanged()
	{
		if (m_NextViewportStartIndex != m_Viewport.startIndex || m_NextViewportEndIndex != m_Viewport.startIndex + m_Viewport.items.Count)
		{
			return true;
		}
		for (int i = 0; i < m_Viewport.items.Count; i++)
		{
			ViewportItem viewportItem = m_Viewport.items[i];
			int num = m_Viewport.startIndex + i;
			if (num >= m_Hierarchy.Length)
			{
				return true;
			}
			if (!viewportItem.EqualsHierarchy(m_Hierarchy[num]))
			{
				return true;
			}
		}
		return false;
	}
```


## Nested types

- `Game.UI.Editor.EditorHierarchyUISystem+CameraMode`  
- `Game.UI.Editor.EditorHierarchyUISystem+ObjectHierarchyJob`  
- `Game.UI.Editor.EditorHierarchyUISystem+PanelItem`  
- `Game.UI.Editor.EditorHierarchyUISystem+Viewport`  
- `Game.UI.Editor.EditorHierarchyUISystem+ViewportItem`  
- `Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem`  
- `Game.UI.Editor.EditorHierarchyUISystem+ItemId`  
- `Game.UI.Editor.EditorHierarchyUISystem+ItemType`  
- `Game.UI.Editor.EditorHierarchyUISystem+EditorHierarchyUISystem_4E004959_LambdaJob_0_Job`  
- `Game.UI.Editor.EditorHierarchyUISystem+TypeHandle`  
- `Game.UI.Editor.EditorHierarchyUISystem+<>c__DisplayClass40_0`  

