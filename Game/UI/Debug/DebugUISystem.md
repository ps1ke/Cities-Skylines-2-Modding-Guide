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
public DebugUISystem();
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
private static UnityEngine.Rendering.DebugUI+Panel GetPanel(System.Int32 panelIndex);
```

- `private static GetPanelCount() : System.Int32`  

```csharp
private static System.Int32 GetPanelCount();
```

- `private static GetPanelIndex(System.String name) : System.Int32`  

```csharp
private static System.Int32 GetPanelIndex(System.String name);
```

- `private GetPanels() : System.Collections.Generic.List<System.String>`  

```csharp
private System.Collections.Generic.List<System.String> GetPanels();
```

- `public Hide() : System.Void`  

```csharp
public System.Void Hide();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SelectNextPanel() : System.Void`  

```csharp
private System.Void SelectNextPanel();
```

- `private SelectPanel(System.Int32 index) : System.Void`  

```csharp
private System.Void SelectPanel(System.Int32 index);
```

- `private SelectPreviousPanel() : System.Void`  

```csharp
private System.Void SelectPreviousPanel();
```

- `public Show() : System.Void`  

```csharp
public System.Void Show();
```

- `public Trigger(Colossal.UI.Binding.IDebugBinding binding) : System.Void`  

```csharp
public System.Void Trigger(Colossal.UI.Binding.IDebugBinding binding);
```

- `private UpdateSelectedPanel() : System.Void`  

```csharp
private System.Void UpdateSelectedPanel();
```


## Nested types

- `Game.UI.Debug.DebugUISystem+Panel`  
- `Game.UI.Debug.DebugUISystem+<>c`  
- `Game.UI.Debug.DebugUISystem+<>c__DisplayClass33_0`  

