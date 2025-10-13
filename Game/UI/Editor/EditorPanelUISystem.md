# Game.UI.Editor.EditorPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class EditorPanelUISystem : Game.UI.UISystemBase
{
    private Game.UI.Editor.IEditorPanel m_LastPanel;
    private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding;
    private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public Game.UI.Editor.IEditorPanel activePanel { get; set; }
    private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get; }

    public EditorPanelUISystem();

    private System.Int32 <OnCreate>b__13_0();
    public static System.Void AddEditorWidgetBindings(Game.UI.Widgets.WidgetBindings widgetBindings);
    private System.Void Cancel();
    private System.Void Close();
    private System.Int32 GetWidth();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
    private System.Void SetWidth(System.Int32 width);
}
```


## Fields

- `private Game.UI.Editor.IEditorPanel m_LastPanel`  

```csharp
private Game.UI.Editor.IEditorPanel m_LastPanel;
```

- `private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField`  

```csharp
private Game.UI.Editor.IEditorPanel <activePanel>k__BackingField;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_ActiveBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Nullable<Game.UI.Localization.LocalizedString>> m_TitleBinding;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
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

- `public Game.UI.Editor.IEditorPanel activePanel { get; set }`  

```csharp
public Game.UI.Editor.IEditorPanel activePanel { get; set; }
```

- `private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get }`  

```csharp
private Game.UI.Editor.EditorPanelWidgetRenderer widgetRenderer { private get; }
```


## Constructors

- `public EditorPanelUISystem()`  

```csharp
[Preserve]
	public EditorPanelUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__13_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_0();
```

- `public static AddEditorWidgetBindings(Game.UI.Widgets.WidgetBindings widgetBindings) : System.Void`  

```csharp
public static void AddEditorWidgetBindings(WidgetBindings widgetBindings)
	{
		widgetBindings.AddDefaultBindings();
		widgetBindings.AddBindings<EditorSection.Bindings>();
		widgetBindings.AddBindings<SeasonsField.Bindings>();
		widgetBindings.AddBindings<IItemPicker.Bindings>();
		widgetBindings.AddBindings<PopupSearchField.Bindings>();
		widgetBindings.AddBindings<AnimationCurveField.Bindings>();
		widgetBindings.AddBindings<LocalizationField.Bindings>();
		widgetBindings.AddBindings<FilterMenu.Bindings>();
		widgetBindings.AddBindings<HierarchyMenu.Bindings>();
		widgetBindings.AddBindings<ExternalLinkField.Bindings>();
		widgetBindings.AddBindings<ListField.Bindings>();
	}
```

- `private Cancel() : System.Void`  

```csharp
private void Cancel()
	{
		if (activePanel != null && activePanel.OnCancel())
		{
			activePanel = null;
		}
	}
```

- `private Close() : System.Void`  

```csharp
private void Close()
	{
		if (activePanel != null && activePanel.OnClose())
		{
			activePanel = null;
		}
	}
```

- `private GetWidth() : System.Int32`  

```csharp
private int GetWidth()
	{
		return (SharedSettings.instance?.editor)?.inspectorWidth ?? 450;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddBinding(m_ActiveBinding = new ValueBinding<bool>("editorPanel", "active", initialValue: false));
		AddBinding(m_TitleBinding = new ValueBinding<LocalizedString?>("editorPanel", "title", null, ValueWritersStruct.Nullable(new ValueWriter<LocalizedString>())));
		AddUpdateBinding(new GetterValueBinding<int>("editorPanel", "width", GetWidth));
		AddUpdateBinding(new GetterValueBinding<int>("editorPanel", "widgetRenderer", () => (int)widgetRenderer));
		AddUpdateBinding(m_WidgetBindings = new WidgetBindings("editorPanel"));
		AddEditorWidgetBindings(m_WidgetBindings);
		m_WidgetBindings.EventValueChanged += OnValueChanged;
		AddBinding(new TriggerBinding("editorPanel", "cancel", Cancel));
		AddBinding(new TriggerBinding("editorPanel", "close", Close));
		AddBinding(new TriggerBinding<int>("editorPanel", "setWidth", SetWidth));
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		activePanel = null;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (activePanel != m_LastPanel)
		{
			if (m_LastPanel is ComponentSystemBase componentSystemBase)
			{
				componentSystemBase.Enabled = false;
				componentSystemBase.Update();
			}
			m_LastPanel = activePanel;
			if (activePanel is ComponentSystemBase componentSystemBase2)
			{
				componentSystemBase2.Enabled = true;
			}
		}
		if (activePanel != null)
		{
			if (activePanel is ComponentSystemBase componentSystemBase3)
			{
				componentSystemBase3.Update();
			}
			m_ActiveBinding.Update(newValue: true);
			m_TitleBinding.Update(activePanel.title);
			m_WidgetBindings.children = activePanel.children;
		}
		else
		{
			m_ActiveBinding.Update(newValue: false);
			m_TitleBinding.Update(null);
			m_WidgetBindings.children = Array.Empty<IWidget>();
		}
		base.OnUpdate();
	}
```

- `public OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
public void OnValueChanged(IWidget widget)
	{
		activePanel?.OnValueChanged(widget);
	}
```

- `private SetWidth(System.Int32 width) : System.Void`  

```csharp
private void SetWidth(int width)
	{
		EditorSettings editorSettings = SharedSettings.instance?.editor;
		if (editorSettings != null)
		{
			editorSettings.inspectorWidth = width;
		}
	}
```


