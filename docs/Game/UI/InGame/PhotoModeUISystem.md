# Game.UI.InGame.PhotoModeUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class PhotoModeUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem;
    private Game.Tools.BulldozeToolSystem m_BulldozeTool;
    private Game.Input.InputBarrier m_ToolBarrier;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding;
    private System.Boolean m_TimeOfDayChanged;
    private System.Boolean <orbitMode>k__BackingField;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding;
    private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField;
    public static const System.String kGroup;

    public System.Boolean orbitMode { get; set; }
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set; }

    public PhotoModeUISystem();

    private System.Boolean <OnCreate>b__22_0();
    public System.Void Activate(System.Boolean enabled);
    private System.Void AddCommonFields(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children, Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private System.Void BindTabNames(Colossal.UI.Binding.IJsonWriter writer);
    private Game.UI.Widgets.Group BuildCheckboxGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private Game.UI.Widgets.IWidget BuildColorGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
    private Game.UI.Widgets.IWidget BuildControl(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private Game.UI.Widgets.Group BuildDropdownGroup(System.String groupName, System.Collections.Generic.List<Game.UI.Widgets.DropdownItem<System.Int32>> items, Game.Reflection.DelegateAccessor<System.Int32> accessor);
    private Game.UI.Widgets.Group BuildEnumGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private Game.UI.Widgets.Group BuildGroupTitle(Game.Rendering.CinematicCamera.PhotoModeProperty property);
    private Game.UI.Widgets.Group BuildMultiPropertyGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
    private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> BuildProperties();
    private Game.UI.Widgets.Group BuildValueGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
    private static System.Collections.IEnumerator CaptureScreenshot();
    private static System.Boolean CheckMultiPropertyHandled(System.Collections.Generic.HashSet<System.String> handledGroupsCache, Game.Rendering.CinematicCamera.PhotoModeProperty property);
    private System.Void InjectPreset(Game.UI.InGame.PhotoModeUIPreset preset);
    private System.Void InjectPresets();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void SelectTab(System.String tabID);
    private System.Void SetCinematicCameraVisible(System.Boolean visible);
    private System.Void SetOverlayHidden(System.Boolean overlayHidden);
    private System.Void TakeScreenshot();
    private System.Void ToggleOrbitCameraActive();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem`  

```csharp
private Game.Rendering.PhotoModeRenderSystem m_PhotoModeRenderSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem`  

```csharp
private Game.UI.InGame.CinematicCameraUISystem m_CinematicCameraUISystem;
```

- `private Game.Tools.BulldozeToolSystem m_BulldozeTool`  

```csharp
private Game.Tools.BulldozeToolSystem m_BulldozeTool;
```

- `private Game.Input.InputBarrier m_ToolBarrier`  

```csharp
private Game.Input.InputBarrier m_ToolBarrier;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_OverlayHiddenBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_OrbitCameraActiveBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_FieldOfViewBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TimeOfDayBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_SaturationBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_AdjustmentCategoriesBinding;
```

- `private System.Boolean m_TimeOfDayChanged`  

```csharp
private System.Boolean m_TimeOfDayChanged;
```

- `private System.Boolean <orbitMode>k__BackingField`  

```csharp
private System.Boolean <orbitMode>k__BackingField;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_CinematicCameraVisibleBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveTabBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TabNamesBinding;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> <tabs>k__BackingField;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Properties

- `public System.Boolean orbitMode { get; set }`  

```csharp
public System.Boolean orbitMode { get; set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> tabs { private get; private set; }
```


## Constructors

- `public PhotoModeUISystem()`  

```csharp
public PhotoModeUISystem();
```


## Methods

- `private <OnCreate>b__22_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__22_0();
```

- `public Activate(System.Boolean enabled) : System.Void`  

```csharp
public System.Void Activate(System.Boolean enabled);
```

- `private AddCommonFields(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children, Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent) : System.Void`  

```csharp
private System.Void AddCommonFields(System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children, Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
```

- `private BindTabNames(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindTabNames(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BuildCheckboxGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  

```csharp
private Game.UI.Widgets.Group BuildCheckboxGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
```

- `private BuildColorGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : Game.UI.Widgets.IWidget`  

```csharp
private Game.UI.Widgets.IWidget BuildColorGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
```

- `private BuildControl(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.IWidget`  

```csharp
private Game.UI.Widgets.IWidget BuildControl(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
```

- `private BuildDropdownGroup(System.String groupName, System.Collections.Generic.List<Game.UI.Widgets.DropdownItem<System.Int32>> items, Game.Reflection.DelegateAccessor<System.Int32> accessor) : Game.UI.Widgets.Group`  

```csharp
private Game.UI.Widgets.Group BuildDropdownGroup(System.String groupName, System.Collections.Generic.List<Game.UI.Widgets.DropdownItem<System.Int32>> items, Game.Reflection.DelegateAccessor<System.Int32> accessor);
```

- `private BuildEnumGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  

```csharp
private Game.UI.Widgets.Group BuildEnumGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
```

- `private BuildGroupTitle(Game.Rendering.CinematicCamera.PhotoModeProperty property) : Game.UI.Widgets.Group`  

```csharp
private Game.UI.Widgets.Group BuildGroupTitle(Game.Rendering.CinematicCamera.PhotoModeProperty property);
```

- `private BuildMultiPropertyGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties) : Game.UI.Widgets.Group`  

```csharp
private Game.UI.Widgets.Group BuildMultiPropertyGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Collections.Generic.IDictionary<System.String, Game.Rendering.CinematicCamera.PhotoModeProperty> allProperties);
```

- `private BuildProperties() : System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab>`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.PhotoModeUISystem+Tab> BuildProperties();
```

- `private BuildValueGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent = False) : Game.UI.Widgets.Group`  

```csharp
private Game.UI.Widgets.Group BuildValueGroup(Game.Rendering.CinematicCamera.PhotoModeProperty property, System.Boolean multiPropertyComponent);
```

- `private static CaptureScreenshot() : System.Collections.IEnumerator`  

```csharp
private static System.Collections.IEnumerator CaptureScreenshot();
```

- `private static CheckMultiPropertyHandled(System.Collections.Generic.HashSet<System.String> handledGroupsCache, Game.Rendering.CinematicCamera.PhotoModeProperty property) : System.Boolean`  

```csharp
private static System.Boolean CheckMultiPropertyHandled(System.Collections.Generic.HashSet<System.String> handledGroupsCache, Game.Rendering.CinematicCamera.PhotoModeProperty property);
```

- `private InjectPreset(Game.UI.InGame.PhotoModeUIPreset preset) : System.Void`  

```csharp
private System.Void InjectPreset(Game.UI.InGame.PhotoModeUIPreset preset);
```

- `private InjectPresets() : System.Void`  

```csharp
private System.Void InjectPresets();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SelectTab(System.String tabID) : System.Void`  

```csharp
private System.Void SelectTab(System.String tabID);
```

- `private SetCinematicCameraVisible(System.Boolean visible) : System.Void`  

```csharp
private System.Void SetCinematicCameraVisible(System.Boolean visible);
```

- `private SetOverlayHidden(System.Boolean overlayHidden) : System.Void`  

```csharp
private System.Void SetOverlayHidden(System.Boolean overlayHidden);
```

- `private TakeScreenshot() : System.Void`  

```csharp
private System.Void TakeScreenshot();
```

- `private ToggleOrbitCameraActive() : System.Void`  

```csharp
private System.Void ToggleOrbitCameraActive();
```


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

