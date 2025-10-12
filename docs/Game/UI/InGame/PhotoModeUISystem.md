# Game.UI.InGame.PhotoModeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem`  
- `private Game.Tools.BulldozeToolSystem m_BulldozeTool`  
- `private Game.Input.InputBarrier m_ToolBarrier`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding`  
- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding`  
- `private System.Boolean m_TimeOfDayChanged`  
- `private System.Boolean <orbitMode>k__BackingField`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding`  
- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  
- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField`  
- `public static const System.String kGroup`  

## Properties

- `public System.Boolean orbitMode { get; set }`  
- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set }`  

## Constructors

- `public PhotoModeUISystem()`  

## Methods

- `private <OnCreate>b__22_0() : System.Boolean`  
- `public Activate(System.Boolean enabled) : System.Void`  
- `private AddCommonFields(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children, Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent) : System.Void`  
- `private BindTabNames(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BuildCheckboxGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  
- `private BuildColorGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : Game.UI.Widgets.IWidget`  
- `private BuildControl(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.IWidget`  
- `private BuildDropdownGroup(System.String groupName, System.Collections.Generic.List<Game.UI.Widgets.DropdownItem<System.Int32>> items, Game.Reflection.DelegateAccessor<System.Int32> accessor) : Game.UI.Widgets.Group`  
- `private BuildEnumGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  
- `private BuildGroupTitle(Game.Rendering.CinematicCamera.PhotoModeProperty property) : Game.UI.Widgets.Group`  
- `private BuildMultiPropertyGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : Game.UI.Widgets.Group`  
- `private BuildProperties() : System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab>`  
- `private BuildValueGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  
- `private static CaptureScreenshot() : System.Collections.IEnumerator`  
- `private static CheckMultiPropertyHandled(System.Collections.Generic.HashSet<System.String> handledGroupsCache, Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.Boolean`  
- `private InjectPreset(Game.UI.InGame.PhotoModeUIPreset preset) : System.Void`  
- `private InjectPresets() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SelectTab(System.String tabID) : System.Void`  
- `private SetCinematicCameraVisible(System.Boolean visible) : System.Void`  
- `private SetOverlayHidden(System.Boolean overlayHidden) : System.Void`  
- `private TakeScreenshot() : System.Void`  
- `private ToggleOrbitCameraActive() : System.Void`  

## Nested types

- `Game.UI.InGame.PhotoModeUISystem+Tab`  
- `Game.UI.InGame.PhotoModeUISystem+<>c`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass37_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass40_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass44_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass45_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass46_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass47_0`  
- `Game.UI.InGame.PhotoModeUISystem+<>c__DisplayClass48_0`  
- `Game.UI.InGame.PhotoModeUISystem+<CaptureScreenshot>d__53`  

