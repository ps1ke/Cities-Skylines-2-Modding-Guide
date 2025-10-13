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
protected EditorPanelSystemBase();
```


## Methods

- `public CloseSubPanel() : System.Void`  

```csharp
public System.Void CloseSubPanel();
```

- `private Game.UI.Editor.IEditorPanel.OnCancel() : System.Boolean`  

```csharp
private System.Boolean Game.UI.Editor.IEditorPanel.OnCancel();
```

- `private Game.UI.Editor.IEditorPanel.OnClose() : System.Boolean`  

```csharp
private System.Boolean Game.UI.Editor.IEditorPanel.OnClose();
```

- `private Game.UI.Editor.IEditorPanel.OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
private System.Void Game.UI.Editor.IEditorPanel.OnValueChanged(Game.UI.Widgets.IWidget widget);
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected virtual System.Boolean OnCancel();
```

- `protected virtual OnClose() : System.Boolean`  

```csharp
protected virtual System.Boolean OnClose();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
```


