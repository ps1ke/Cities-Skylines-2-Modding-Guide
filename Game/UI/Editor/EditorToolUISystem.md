# Game.UI.Editor.EditorToolUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class EditorToolUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
    private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding;
    private Game.UI.Editor.IEditorTool[] m_Tools;
    private System.Boolean[] m_Disabled;
    private Game.UI.Editor.IEditorTool m_ActiveTool;
    private Unity.Entities.Entity m_LastSelectedEntity;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public Game.UI.Editor.IEditorTool[] tools { get; set; }
    public Game.UI.Editor.IEditorTool activeTool { get; set; }

    public EditorToolUISystem();

    private Game.UI.Editor.IEditorTool[] <OnCreate>b__17_0();
    private System.String <OnCreate>b__17_1();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void SelectEntity(Unity.Entities.Entity entity);
    public System.Void SelectEntitySubMesh(Unity.Entities.Entity entity, System.Int32 subMeshIndex);
    public System.Void SelectTool(System.String id);
    private System.Boolean UpdateToolState();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  

```csharp
private Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
```

- `private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem`  

```csharp
private Game.UI.Editor.InspectorPanelSystem m_InspectorPanelSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.Editor.IEditorTool[]> m_ToolsBinding;
```

- `private Game.UI.Editor.IEditorTool[] m_Tools`  

```csharp
private Game.UI.Editor.IEditorTool[] m_Tools;
```

- `private System.Boolean[] m_Disabled`  

```csharp
private System.Boolean[] m_Disabled;
```

- `private Game.UI.Editor.IEditorTool m_ActiveTool`  

```csharp
private Game.UI.Editor.IEditorTool m_ActiveTool;
```

- `private Unity.Entities.Entity m_LastSelectedEntity`  

```csharp
private Unity.Entities.Entity m_LastSelectedEntity;
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

- `public Game.UI.Editor.IEditorTool[] tools { get; set }`  

```csharp
public Game.UI.Editor.IEditorTool[] tools { get; set; }
```

- `public Game.UI.Editor.IEditorTool activeTool { get; set }`  

```csharp
public Game.UI.Editor.IEditorTool activeTool { get; set; }
```


## Constructors

- `public EditorToolUISystem()`  

```csharp
[Preserve]
	public EditorToolUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__17_0() : Game.UI.Editor.IEditorTool[]`  

```csharp
private Game.UI.Editor.IEditorTool[] <OnCreate>b__17_0();
```

- `private <OnCreate>b__17_1() : System.String`  

```csharp
private System.String <OnCreate>b__17_1();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_EditorPanelUISystem = base.World.GetOrCreateSystemManaged<EditorPanelUISystem>();
		m_InspectorPanelSystem = base.World.GetOrCreateSystemManaged<InspectorPanelSystem>();
		tools = new IEditorTool[6]
		{
			new EditorAssetImportTool(base.World),
			new EditorTerrainTool(base.World),
			new EditorPrefabTool(base.World),
			new EditorPrefabEditorTool(base.World),
			new EditorPhotoTool(base.World),
			new EditorBulldozeTool(base.World)
		};
		AddUpdateBinding(m_ToolsBinding = new GetterValueBinding<IEditorTool[]>("editorTool", "tools", () => tools, new ArrayWriter<IEditorTool>(new ValueWriter<IEditorTool>())));
		AddUpdateBinding(new GetterValueBinding<string>("editorTool", "activeTool", () => activeTool?.id, ValueWriters.Nullable(new StringWriter())));
		AddBinding(new TriggerBinding<string>("editorTool", "selectTool", SelectTool));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (activeTool != null && !activeTool.active)
		{
			activeTool = null;
		}
		if (m_ToolSystem.selected != m_LastSelectedEntity)
		{
			SelectEntity(m_ToolSystem.selected);
		}
		if (UpdateToolState())
		{
			m_ToolsBinding.TriggerUpdate();
		}
	}
```

- `public SelectEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
public void SelectEntity(Entity entity)
	{
		m_LastSelectedEntity = entity;
		if (m_InspectorPanelSystem.SelectEntity(entity))
		{
			activeTool = null;
			m_EditorPanelUISystem.activePanel = m_InspectorPanelSystem;
		}
		else if (m_EditorPanelUISystem.activePanel == m_InspectorPanelSystem)
		{
			m_EditorPanelUISystem.activePanel = null;
		}
	}
```

- `public SelectEntitySubMesh(Unity.Entities.Entity entity, System.Int32 subMeshIndex) : System.Void`  

```csharp
public void SelectEntitySubMesh(Entity entity, int subMeshIndex)
	{
		m_LastSelectedEntity = entity;
		if (m_InspectorPanelSystem.SelectMesh(entity, subMeshIndex))
		{
			activeTool = null;
			m_EditorPanelUISystem.activePanel = m_InspectorPanelSystem;
		}
		else if (m_EditorPanelUISystem.activePanel == m_InspectorPanelSystem)
		{
			m_EditorPanelUISystem.activePanel = null;
		}
	}
```

- `public SelectTool(System.String id) : System.Void`  

```csharp
public void SelectTool([CanBeNull] string id)
	{
		activeTool = tools.FirstOrDefault((IEditorTool t) => t.id == id);
	}
```

- `private UpdateToolState() : System.Boolean`  

```csharp
private bool UpdateToolState()
	{
		bool result = false;
		for (int i = 0; i < m_Tools.Length; i++)
		{
			bool disabled = m_Tools[i].disabled;
			if (disabled != m_Disabled[i])
			{
				m_Disabled[i] = disabled;
				result = true;
			}
		}
		return result;
	}
```


## Nested types

- `Game.UI.Editor.EditorToolUISystem+<>c`  
- `Game.UI.Editor.EditorToolUISystem+<>c__DisplayClass21_0`  

