# Game.UI.Debug.DebugUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Debug`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class DebugUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EnabledBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibleBinding;
    private Colossal.UI.Binding.ValueBinding<Game.UI.Debug.DebugUISystem+Panel> m_SelectedPanelBinding;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private Colossal.UI.Binding.ValueBinding<Colossal.UI.Binding.IDebugBinding> m_ObservedBindingBinding;
    private Colossal.UI.Binding.EventBinding<Colossal.UI.Binding.IDebugBinding> m_BindingTriggeredBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch>> m_WatchesBinding;
    private System.String m_SelectedPanel;
    private System.Boolean m_ShowDeveloperInfo;
    private static const System.String kGroup;

    public System.Boolean visible { get; }
    public Colossal.UI.Binding.IDebugBinding observedBinding { get; set; }
    private System.String selectedPanel { private get; private set; }
    public System.Boolean developerInfoVisible { get; set; }
    private static System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Panel> visiblePanels { private get; }
    private static System.Boolean debugSystemEnabled { private get; }

    public DebugUISystem();

    private System.Int32 <OnCreate>b__21_0();
    private System.Boolean <OnCreate>b__21_1();
    private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> <OnCreate>b__21_2();
    private System.Void <Show>b__24_0(System.Int32 msg, System.Boolean dismiss);
    private static UnityEngine.Rendering.DebugUI+Panel GetPanel(System.Int32 panelIndex);
    private static System.Int32 GetPanelCount();
    private static System.Int32 GetPanelIndex(System.String name);
    private System.Collections.Generic.List<System.String> GetPanels();
    public System.Void Hide();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void SelectNextPanel();
    private System.Void SelectPanel(System.Int32 index);
    private System.Void SelectPreviousPanel();
    public System.Void Show();
    public System.Void Trigger(Colossal.UI.Binding.IDebugBinding binding);
    private System.Void UpdateSelectedPanel();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EnabledBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EnabledBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibleBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.Debug.DebugUISystem+Panel> m_SelectedPanelBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.Debug.DebugUISystem+Panel> m_SelectedPanelBinding;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private Colossal.UI.Binding.ValueBinding<Colossal.UI.Binding.IDebugBinding> m_ObservedBindingBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Colossal.UI.Binding.IDebugBinding> m_ObservedBindingBinding;
```

- `private Colossal.UI.Binding.EventBinding<Colossal.UI.Binding.IDebugBinding> m_BindingTriggeredBinding`  

```csharp
private Colossal.UI.Binding.EventBinding<Colossal.UI.Binding.IDebugBinding> m_BindingTriggeredBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch>> m_WatchesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch>> m_WatchesBinding;
```

- `private System.String m_SelectedPanel`  

```csharp
private System.String m_SelectedPanel;
```

- `private System.Boolean m_ShowDeveloperInfo`  

```csharp
private System.Boolean m_ShowDeveloperInfo;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public System.Boolean visible { get }`  

```csharp
public System.Boolean visible { get; }
```

- `public Colossal.UI.Binding.IDebugBinding observedBinding { get; set }`  

```csharp
public Colossal.UI.Binding.IDebugBinding observedBinding { get; set; }
```

- `private System.String selectedPanel { private get; private set }`  

```csharp
private System.String selectedPanel { private get; private set; }
```

- `public System.Boolean developerInfoVisible { get; set }`  

```csharp
public System.Boolean developerInfoVisible { get; set; }
```

- `private static System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Panel> visiblePanels { private get }`  

```csharp
private static System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Panel> visiblePanels { private get; }
```

- `private static System.Boolean debugSystemEnabled { private get }`  

```csharp
private static System.Boolean debugSystemEnabled { private get; }
```


## Constructors

- `public DebugUISystem()`  

```csharp
[Preserve]
	public DebugUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__21_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__21_0();
```

- `private <OnCreate>b__21_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__21_1();
```

- `private <OnCreate>b__21_2() : System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch>`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> <OnCreate>b__21_2();
```

- `private <Show>b__24_0(System.Int32 msg, System.Boolean dismiss) : System.Void`  

```csharp
private System.Void <Show>b__24_0(System.Int32 msg, System.Boolean dismiss);
```

- `private static GetPanel(System.Int32 panelIndex) : UnityEngine.Rendering.DebugUI+Panel`  

```csharp
[CanBeNull]
	private static DebugUI.Panel GetPanel(int panelIndex)
	{
		if (panelIndex < 0)
		{
			return null;
		}
		return visiblePanels.Skip(panelIndex).FirstOrDefault();
	}
```

- `private static GetPanelCount() : System.Int32`  

```csharp
private static int GetPanelCount()
	{
		return visiblePanels.Count();
	}
```

- `private static GetPanelIndex(System.String name) : System.Int32`  

```csharp
private static int GetPanelIndex(string name)
	{
		return visiblePanels.ToList().FindIndex((DebugUI.Panel panel) => panel.displayName == name);
	}
```

- `private GetPanels() : System.Collections.Generic.List<System.String>`  

```csharp
private List<string> GetPanels()
	{
		return visiblePanels.Select((DebugUI.Panel p) => p.displayName).ToList();
	}
```

- `public Hide() : System.Void`  

```csharp
public void Hide()
	{
		if (visible)
		{
			m_VisibleBinding.Update(newValue: false);
			base.World.GetOrCreateSystemManaged<DebugSystem>().Enabled = false;
			UpdateSelectedPanel();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddBinding(m_EnabledBinding = new ValueBinding<bool>("debug", "enabled", debugSystemEnabled));
		AddBinding(m_VisibleBinding = new ValueBinding<bool>("debug", "visible", initialValue: false));
		AddUpdateBinding(new GetterValueBinding<List<string>>("debug", "panels", GetPanels, new ListWriter<string>()));
		AddUpdateBinding(new GetterValueBinding<int>("debug", "selectedIndex", () => GetPanelIndex(selectedPanel)));
		AddBinding(m_SelectedPanelBinding = new ValueBinding<Panel>("debug", "selectedPanel", null, ValueWriters.Nullable(new ValueWriter<Panel>())));
		AddUpdateBinding(m_WidgetBindings = new WidgetBindings("debug"));
		m_WidgetBindings.AddDefaultBindings();
		AddBinding(m_ObservedBindingBinding = new ValueBinding<IDebugBinding>("debug", "observedBinding", null, ValueWriters.Nullable(new DebugBindingWriter())));
		AddBinding(m_BindingTriggeredBinding = new EventBinding<IDebugBinding>("debug", "bindingTriggered", new DebugBindingWriter()));
		AddUpdateBinding(new GetterValueBinding<bool>("debug", "developerInfoVisible", () => developerInfoVisible));
		AddBinding(m_WatchesBinding = new GetterValueBinding<List<DebugWatchSystem.Watch>>("debug", "watches", () => base.World.GetOrCreateSystemManaged<DebugWatchSystem>().watches, new ListWriter<DebugWatchSystem.Watch>(new ValueWriter<DebugWatchSystem.Watch>())));
		AddBinding(new TriggerBinding("debug", "show", Show));
		AddBinding(new TriggerBinding("debug", "hide", Hide));
		AddBinding(new TriggerBinding<int>("debug", "selectPanel", SelectPanel));
		AddBinding(new TriggerBinding("debug", "selectPreviousPanel", SelectPreviousPanel));
		AddBinding(new TriggerBinding("debug", "selectNextPanel", SelectNextPanel));
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (visible)
		{
			UpdateSelectedPanel();
			DebugWatchSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<DebugWatchSystem>();
			if (orCreateSystemManaged.watchesChanged)
			{
				m_WatchesBinding.TriggerUpdate();
				orCreateSystemManaged.ClearWatchesChanged();
			}
		}
		base.OnUpdate();
	}
```

- `private SelectNextPanel() : System.Void`  

```csharp
private void SelectNextPanel()
	{
		if (!visible)
		{
			return;
		}
		int panelCount = GetPanelCount();
		if (panelCount != 0)
		{
			int panelIndex = GetPanelIndex(selectedPanel);
			if (panelIndex < 0 || panelIndex >= panelCount - 1)
			{
				SelectPanel(0);
			}
			else
			{
				SelectPanel(panelIndex + 1);
			}
		}
	}
```

- `private SelectPanel(System.Int32 index) : System.Void`  

```csharp
private void SelectPanel(int index)
	{
		if (visible)
		{
			selectedPanel = GetPanel(index)?.displayName;
			UpdateSelectedPanel();
		}
	}
```

- `private SelectPreviousPanel() : System.Void`  

```csharp
private void SelectPreviousPanel()
	{
		if (!visible)
		{
			return;
		}
		int panelCount = GetPanelCount();
		if (panelCount != 0)
		{
			int panelIndex = GetPanelIndex(selectedPanel);
			if (panelIndex <= 0 || panelIndex >= panelCount)
			{
				SelectPanel(panelCount - 1);
			}
			else
			{
				SelectPanel(panelIndex - 1);
			}
		}
	}
```

- `public Show() : System.Void`  

```csharp
public void Show()
	{
		if (visible || !m_EnabledBinding.value)
		{
			return;
		}
		m_VisibleBinding.Update(newValue: true);
		if (!SharedSettings.instance.userInterface.dismissedConfirmations.Contains("DebugMenu") && PlatformManager.instance.achievementsEnabled)
		{
			GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new DismissibleConfirmationDialog("Common.DIALOG_TITLE[Warning]", "Common.DIALOG_MESSAGE[DisableAchievements]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), delegate(int msg, bool dismiss)
			{
				if (msg == 0)
				{
					if (dismiss)
					{
						SharedSettings.instance.userInterface.dismissedConfirmations.Add("DebugMenu");
						SharedSettings.instance.userInterface.ApplyAndSave();
					}
					base.World.GetOrCreateSystemManaged<DebugSystem>().Enabled = true;
					PlatformManager.instance.achievementsEnabled = false;
				}
			});
		}
		else
		{
			base.World.GetOrCreateSystemManaged<DebugSystem>().Enabled = true;
			PlatformManager.instance.achievementsEnabled = false;
		}
		UpdateSelectedPanel();
	}
```

- `public Trigger(Colossal.UI.Binding.IDebugBinding binding) : System.Void`  

```csharp
public void Trigger(IDebugBinding binding)
	{
		m_BindingTriggeredBinding.Trigger(binding);
	}
```

- `private UpdateSelectedPanel() : System.Void`  

```csharp
private void UpdateSelectedPanel()
	{
		Panel value = m_SelectedPanelBinding.value;
		DebugUI.Panel obj = value?.panel;
		DebugUI.Panel panel = (visible ? GetPanel(GetPanelIndex(selectedPanel)) : null);
		if (obj != panel)
		{
			value?.Dispose();
			m_SelectedPanelBinding.Update((panel != null) ? new Panel(panel) : null);
			m_WidgetBindings.children = ((m_SelectedPanelBinding.value != null) ? m_SelectedPanelBinding.value.children : new List<IWidget>());
		}
		else if (value != null && value.Update())
		{
			m_SelectedPanelBinding.TriggerUpdate();
			m_WidgetBindings.children = ((m_SelectedPanelBinding.value != null) ? m_SelectedPanelBinding.value.children : new List<IWidget>());
		}
	}
```


## Nested types

- `Game.UI.Debug.DebugUISystem+Panel`  
- `Game.UI.Debug.DebugUISystem+<>c`  
- `Game.UI.Debug.DebugUISystem+<>c__DisplayClass33_0`  

