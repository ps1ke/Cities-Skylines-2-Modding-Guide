# Game.UI.Debug.DebugUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Debug`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EnabledBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibleBinding`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.Debug.DebugUISystem+Panel> m_SelectedPanelBinding`  
- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  
- `private Colossal.UI.Binding.ValueBinding<Colossal.UI.Binding.IDebugBinding> m_ObservedBindingBinding`  
- `private Colossal.UI.Binding.EventBinding<Colossal.UI.Binding.IDebugBinding> m_BindingTriggeredBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch>> m_WatchesBinding`  
- `private System.String m_SelectedPanel`  
- `private System.Boolean m_ShowDeveloperInfo`  
- `private static const System.String kGroup`  

## Properties

- `public System.Boolean visible { get }`  
- `public Colossal.UI.Binding.IDebugBinding observedBinding { get; set }`  
- `private System.String selectedPanel { private get; private set }`  
- `public System.Boolean developerInfoVisible { get; set }`  
- `private static System.Collections.Generic.IEnumerable<UnityEngine.Rendering.DebugUI+Panel> visiblePanels { private get }`  
- `private static System.Boolean debugSystemEnabled { private get }`  

## Constructors

- `public DebugUISystem()`  

## Methods

- `private <OnCreate>b__21_0() : System.Int32`  
- `private <OnCreate>b__21_1() : System.Boolean`  
- `private <OnCreate>b__21_2() : System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch>`  
- `private <Show>b__24_0(System.Int32 msg, System.Boolean dismiss) : System.Void`  
- `private static GetPanel(System.Int32 panelIndex) : UnityEngine.Rendering.DebugUI+Panel`  
- `private static GetPanelCount() : System.Int32`  
- `private static GetPanelIndex(System.String name) : System.Int32`  
- `private GetPanels() : System.Collections.Generic.List<System.String>`  
- `public Hide() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SelectNextPanel() : System.Void`  
- `private SelectPanel(System.Int32 index) : System.Void`  
- `private SelectPreviousPanel() : System.Void`  
- `public Show() : System.Void`  
- `public Trigger(Colossal.UI.Binding.IDebugBinding binding) : System.Void`  
- `private UpdateSelectedPanel() : System.Void`  

## Nested types

- `Game.UI.Debug.DebugUISystem+Panel`  
- `Game.UI.Debug.DebugUISystem+<>c`  
- `Game.UI.Debug.DebugUISystem+<>c__DisplayClass33_0`  

