# Game.UI.Editor.EditorPanelSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

## Code

```csharp
public abstract class EditorPanelSystemBase : Game.GameSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.UI.Editor.IEditorPanel m_LastSubPanel;
    private Game.UI.Editor.IEditorPanel <activeSubPanel>k__BackingField;
    private Game.UI.Localization.LocalizedString <title>k__BackingField;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
    private readonly Colossal.Logging.ILog <log>k__BackingField;

    protected Game.UI.Editor.IEditorPanel activeSubPanel { protected get; protected set; }
    protected Game.UI.Localization.LocalizedString title { protected get; protected set; }
    protected System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { protected get; protected set; }
    public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }
    protected Colossal.Logging.ILog log { protected get; }
    private Game.UI.Localization.LocalizedString Game.UI.Editor.IEditorPanel.title { private get; }
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> Game.UI.Editor.IEditorPanel.children { private get; }

    protected EditorPanelSystemBase();

    public System.Void CloseSubPanel();
    private System.Boolean Game.UI.Editor.IEditorPanel.OnCancel();
    private System.Boolean Game.UI.Editor.IEditorPanel.OnClose();
    private System.Void Game.UI.Editor.IEditorPanel.OnValueChanged(Game.UI.Widgets.IWidget widget);
    protected virtual System.Boolean OnCancel();
    protected virtual System.Boolean OnClose();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
}
```


## Fields

- `private Game.UI.Editor.IEditorPanel m_LastSubPanel`  

```csharp
private Game.UI.Editor.IEditorPanel m_LastSubPanel;
```

- `private Game.UI.Editor.IEditorPanel <activeSubPanel>k__BackingField`  

```csharp
private Game.UI.Editor.IEditorPanel <activeSubPanel>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString <title>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <title>k__BackingField;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField;
```

- `private readonly Colossal.Logging.ILog <log>k__BackingField`  

```csharp
private readonly Colossal.Logging.ILog <log>k__BackingField;
```


## Properties

- `protected Game.UI.Editor.IEditorPanel activeSubPanel { protected get; protected set }`  

```csharp
protected Game.UI.Editor.IEditorPanel activeSubPanel { protected get; protected set; }
```

- `protected Game.UI.Localization.LocalizedString title { protected get; protected set }`  

```csharp
protected Game.UI.Localization.LocalizedString title { protected get; protected set; }
```

- `protected System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { protected get; protected set }`  

```csharp
protected System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { protected get; protected set; }
```

- `public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get }`  

```csharp
public Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { get; }
```

- `protected Colossal.Logging.ILog log { protected get }`  

```csharp
protected Colossal.Logging.ILog log { protected get; }
```

- `private Game.UI.Localization.LocalizedString Game.UI.Editor.IEditorPanel.title { private get }`  

```csharp
private Game.UI.Localization.LocalizedString Game.UI.Editor.IEditorPanel.title { private get; }
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> Game.UI.Editor.IEditorPanel.children { private get }`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> Game.UI.Editor.IEditorPanel.children { private get; }
```


## Constructors

- `protected EditorPanelSystemBase()`  

```csharp
[Preserve]
	protected EditorPanelSystemBase()
	{
	}
```


## Methods

- `public CloseSubPanel() : System.Void`  

```csharp
public void CloseSubPanel()
	{
		activeSubPanel = null;
	}
```

- `private Game.UI.Editor.IEditorPanel.OnCancel() : System.Boolean`  

```csharp
protected virtual bool OnCancel()
	{
		return OnClose();
	}
```

- `private Game.UI.Editor.IEditorPanel.OnClose() : System.Boolean`  

```csharp
protected virtual bool OnClose()
	{
		return true;
	}
```

- `private Game.UI.Editor.IEditorPanel.OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected virtual void OnValueChanged(IWidget widget)
	{
	}
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected virtual bool OnCancel()
	{
		return OnClose();
	}
```

- `protected virtual OnClose() : System.Boolean`  

```csharp
protected virtual bool OnClose()
	{
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (activeSubPanel != m_LastSubPanel)
		{
			if (m_LastSubPanel is ComponentSystemBase componentSystemBase)
			{
				componentSystemBase.Enabled = false;
				componentSystemBase.Update();
			}
			m_LastSubPanel = activeSubPanel;
			if (activeSubPanel is ComponentSystemBase componentSystemBase2)
			{
				componentSystemBase2.Enabled = true;
			}
		}
		if (activeSubPanel is ComponentSystemBase componentSystemBase3)
		{
			componentSystemBase3.Update();
		}
	}
```

- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected virtual void OnValueChanged(IWidget widget)
	{
	}
```


