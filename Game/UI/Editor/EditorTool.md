# Game.UI.Editor.EditorTool

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.IEditorTool`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IUITagProvider`  

## Code

```csharp
public class EditorTool : Game.UI.Editor.IEditorTool, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IUITagProvider
{
    private System.String <id>k__BackingField;
    private System.String <icon>k__BackingField;
    private System.Boolean <disabled>k__BackingField;
    private System.String <shortcut>k__BackingField;
    private System.String <uiTag>k__BackingField;
    private Game.UI.Editor.IEditorPanel <panel>k__BackingField;
    private Game.Tools.ToolBaseSystem <tool>k__BackingField;
    protected Game.Tools.ToolSystem m_ToolSystem;
    protected Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;

    public System.String id { get; set; }
    public System.String icon { get; set; }
    public System.Boolean disabled { get; set; }
    public System.String shortcut { get; set; }
    public System.String uiTag { get; set; }
    public Game.UI.Editor.IEditorPanel panel { get; set; }
    public Game.Tools.ToolBaseSystem tool { get; set; }
    public System.Boolean active { get; set; }

    public EditorTool(Unity.Entities.World world);

    protected virtual System.Boolean IsActive();
    protected virtual System.Void OnDisable();
    protected virtual System.Void OnEnable();
}
```


## Fields

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```

- `private System.Boolean <disabled>k__BackingField`  

```csharp
private System.Boolean <disabled>k__BackingField;
```

- `private System.String <shortcut>k__BackingField`  

```csharp
private System.String <shortcut>k__BackingField;
```

- `private System.String <uiTag>k__BackingField`  

```csharp
private System.String <uiTag>k__BackingField;
```

- `private Game.UI.Editor.IEditorPanel <panel>k__BackingField`  

```csharp
private Game.UI.Editor.IEditorPanel <panel>k__BackingField;
```

- `private Game.Tools.ToolBaseSystem <tool>k__BackingField`  

```csharp
private Game.Tools.ToolBaseSystem <tool>k__BackingField;
```

- `protected Game.Tools.ToolSystem m_ToolSystem`  

```csharp
protected Game.Tools.ToolSystem m_ToolSystem;
```

- `protected Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem`  

```csharp
protected Game.UI.Editor.EditorPanelUISystem m_EditorPanelUISystem;
```


## Properties

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```

- `public System.Boolean disabled { get; set }`  

```csharp
public System.Boolean disabled { get; set; }
```

- `public System.String shortcut { get; set }`  

```csharp
public System.String shortcut { get; set; }
```

- `public System.String uiTag { get; set }`  

```csharp
public System.String uiTag { get; set; }
```

- `public Game.UI.Editor.IEditorPanel panel { get; set }`  

```csharp
public Game.UI.Editor.IEditorPanel panel { get; set; }
```

- `public Game.Tools.ToolBaseSystem tool { get; set }`  

```csharp
public Game.Tools.ToolBaseSystem tool { get; set; }
```

- `public System.Boolean active { get; set }`  

```csharp
public System.Boolean active { get; set; }
```


## Constructors

- `public EditorTool(Unity.Entities.World world)`  

```csharp
public EditorTool(World world)
	{
		m_ToolSystem = world.GetOrCreateSystemManaged<ToolSystem>();
		m_EditorPanelUISystem = world.GetOrCreateSystemManaged<EditorPanelUISystem>();
	}
```


## Methods

- `protected virtual IsActive() : System.Boolean`  

```csharp
protected virtual bool IsActive()
	{
		if (m_EditorPanelUISystem.activePanel == panel)
		{
			if (tool != null)
			{
				return m_ToolSystem.activeTool == tool;
			}
			return true;
		}
		return false;
	}
```

- `protected virtual OnDisable() : System.Void`  

```csharp
protected virtual void OnDisable()
	{
		if (m_EditorPanelUISystem.activePanel == panel)
		{
			m_EditorPanelUISystem.activePanel = null;
		}
		if (tool != null && m_ToolSystem.activeTool == tool)
		{
			m_ToolSystem.ActivatePrefabTool(null);
		}
	}
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected virtual void OnEnable()
	{
		m_ToolSystem.selected = Entity.Null;
		m_EditorPanelUISystem.activePanel = panel;
		if (tool != null)
		{
			m_ToolSystem.activeTool = tool;
		}
	}
```


