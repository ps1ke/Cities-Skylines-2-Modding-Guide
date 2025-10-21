# Game.Settings.InputSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUITabOrder`, `SettingsUIGroupOrder`, `SettingsUITabWarning`, `SettingsUITabWarning`, `SettingsUITabWarning`  

## Code

```csharp
public class InputSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <elevationDraggingEnabled>k__BackingField;
    private System.Single <mouseScrollSensitivity>k__BackingField;
    private System.Single <keyboardMoveSensitivity>k__BackingField;
    private System.Single <keyboardRotateSensitivity>k__BackingField;
    private System.Single <keyboardZoomSensitivity>k__BackingField;
    private System.Single <mouseMoveSensitivity>k__BackingField;
    private System.Single <mouseRotateSensitivity>k__BackingField;
    private System.Single <mouseZoomSensitivity>k__BackingField;
    private System.Boolean <mouseInvertX>k__BackingField;
    private System.Boolean <mouseInvertY>k__BackingField;
    private System.Single <gamepadMoveSensitivity>k__BackingField;
    private System.Single <gamepadRotateSensitivity>k__BackingField;
    private System.Single <gamepadZoomSensitivity>k__BackingField;
    private System.Boolean <gamepadInvertX>k__BackingField;
    private System.Boolean <gamepadInvertY>k__BackingField;
    public static const System.String kName;
    public static const System.String kMiscTab;

    public System.Boolean elevationDraggingEnabled { get; set; }
    public System.Single mouseScrollSensitivity { get; set; }
    public System.Single finalScrollSensitivity { get; }
    public System.Single keyboardMoveSensitivity { get; set; }
    public System.Single keyboardRotateSensitivity { get; set; }
    public System.Single keyboardZoomSensitivity { get; set; }
    public System.Single mouseMoveSensitivity { get; set; }
    public System.Single mouseRotateSensitivity { get; set; }
    public System.Single mouseZoomSensitivity { get; set; }
    public System.Boolean mouseInvertX { get; set; }
    public System.Boolean mouseInvertY { get; set; }
    public System.Single gamepadMoveSensitivity { get; set; }
    public System.Single gamepadRotateSensitivity { get; set; }
    public System.Single gamepadZoomSensitivity { get; set; }
    public System.Boolean gamepadInvertX { get; set; }
    public System.Boolean gamepadInvertY { get; set; }
    private System.Boolean isKeyboardConflict { private get; }
    private System.Boolean isMouseConflict { private get; }
    private System.Boolean isGamepadConflict { private get; }

    public InputSettings();

    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    private System.Void GetPageSection(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Input.InputManager+DeviceType device);
    private System.String[] GetTabOrder();
    public virtual System.Void SetDefaults();
    private System.Void SetDefaultsForDevice(Game.Input.InputManager+DeviceType device);
}
```


## Fields

- `private System.Boolean <elevationDraggingEnabled>k__BackingField`  

```csharp
private System.Boolean <elevationDraggingEnabled>k__BackingField;
```

- `private System.Single <mouseScrollSensitivity>k__BackingField`  

```csharp
private System.Single <mouseScrollSensitivity>k__BackingField;
```

- `private System.Single <keyboardMoveSensitivity>k__BackingField`  

```csharp
private System.Single <keyboardMoveSensitivity>k__BackingField;
```

- `private System.Single <keyboardRotateSensitivity>k__BackingField`  

```csharp
private System.Single <keyboardRotateSensitivity>k__BackingField;
```

- `private System.Single <keyboardZoomSensitivity>k__BackingField`  

```csharp
private System.Single <keyboardZoomSensitivity>k__BackingField;
```

- `private System.Single <mouseMoveSensitivity>k__BackingField`  

```csharp
private System.Single <mouseMoveSensitivity>k__BackingField;
```

- `private System.Single <mouseRotateSensitivity>k__BackingField`  

```csharp
private System.Single <mouseRotateSensitivity>k__BackingField;
```

- `private System.Single <mouseZoomSensitivity>k__BackingField`  

```csharp
private System.Single <mouseZoomSensitivity>k__BackingField;
```

- `private System.Boolean <mouseInvertX>k__BackingField`  

```csharp
private System.Boolean <mouseInvertX>k__BackingField;
```

- `private System.Boolean <mouseInvertY>k__BackingField`  

```csharp
private System.Boolean <mouseInvertY>k__BackingField;
```

- `private System.Single <gamepadMoveSensitivity>k__BackingField`  

```csharp
private System.Single <gamepadMoveSensitivity>k__BackingField;
```

- `private System.Single <gamepadRotateSensitivity>k__BackingField`  

```csharp
private System.Single <gamepadRotateSensitivity>k__BackingField;
```

- `private System.Single <gamepadZoomSensitivity>k__BackingField`  

```csharp
private System.Single <gamepadZoomSensitivity>k__BackingField;
```

- `private System.Boolean <gamepadInvertX>k__BackingField`  

```csharp
private System.Boolean <gamepadInvertX>k__BackingField;
```

- `private System.Boolean <gamepadInvertY>k__BackingField`  

```csharp
private System.Boolean <gamepadInvertY>k__BackingField;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `public static const System.String kMiscTab`  

```csharp
public static const System.String kMiscTab;
```


## Properties

- `public System.Boolean elevationDraggingEnabled { get; set }`  

```csharp
public System.Boolean elevationDraggingEnabled { get; set; }
```

- `public System.Single mouseScrollSensitivity { get; set }`  

```csharp
public System.Single mouseScrollSensitivity { get; set; }
```

- `public System.Single finalScrollSensitivity { get }`  

```csharp
public System.Single finalScrollSensitivity { get; }
```

- `public System.Single keyboardMoveSensitivity { get; set }`  

```csharp
public System.Single keyboardMoveSensitivity { get; set; }
```

- `public System.Single keyboardRotateSensitivity { get; set }`  

```csharp
public System.Single keyboardRotateSensitivity { get; set; }
```

- `public System.Single keyboardZoomSensitivity { get; set }`  

```csharp
public System.Single keyboardZoomSensitivity { get; set; }
```

- `public System.Single mouseMoveSensitivity { get; set }`  

```csharp
public System.Single mouseMoveSensitivity { get; set; }
```

- `public System.Single mouseRotateSensitivity { get; set }`  

```csharp
public System.Single mouseRotateSensitivity { get; set; }
```

- `public System.Single mouseZoomSensitivity { get; set }`  

```csharp
public System.Single mouseZoomSensitivity { get; set; }
```

- `public System.Boolean mouseInvertX { get; set }`  

```csharp
public System.Boolean mouseInvertX { get; set; }
```

- `public System.Boolean mouseInvertY { get; set }`  

```csharp
public System.Boolean mouseInvertY { get; set; }
```

- `public System.Single gamepadMoveSensitivity { get; set }`  

```csharp
public System.Single gamepadMoveSensitivity { get; set; }
```

- `public System.Single gamepadRotateSensitivity { get; set }`  

```csharp
public System.Single gamepadRotateSensitivity { get; set; }
```

- `public System.Single gamepadZoomSensitivity { get; set }`  

```csharp
public System.Single gamepadZoomSensitivity { get; set; }
```

- `public System.Boolean gamepadInvertX { get; set }`  

```csharp
public System.Boolean gamepadInvertX { get; set; }
```

- `public System.Boolean gamepadInvertY { get; set }`  

```csharp
public System.Boolean gamepadInvertY { get; set; }
```

- `private System.Boolean isKeyboardConflict { private get }`  

```csharp
private System.Boolean isKeyboardConflict { private get; }
```

- `private System.Boolean isMouseConflict { private get }`  

```csharp
private System.Boolean isMouseConflict { private get; }
```

- `private System.Boolean isGamepadConflict { private get }`  

```csharp
private System.Boolean isGamepadConflict { private get; }
```


## Constructors

- `public InputSettings()`  

```csharp
public InputSettings();
```


## Methods

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
```

- `private GetPageSection(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Input.InputManager+DeviceType device) : System.Void`  

```csharp
private System.Void GetPageSection(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Input.InputManager+DeviceType device);
```

- `private GetTabOrder() : System.String[]`  

```csharp
private System.String[] GetTabOrder();
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```

- `private SetDefaultsForDevice(Game.Input.InputManager+DeviceType device) : System.Void`  

```csharp
private System.Void SetDefaultsForDevice(Game.Input.InputManager+DeviceType device);
```


## Nested types

- `Game.Settings.InputSettings+<>c`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_0`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_1`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_2`  

