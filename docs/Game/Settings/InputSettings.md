# Game.Settings.InputSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUITabOrder`, `SettingsUIGroupOrder`, `SettingsUITabWarning`, `SettingsUITabWarning`, `SettingsUITabWarning`  

## Fields

- `private System.Boolean <elevationDraggingEnabled>k__BackingField`  
- `private System.Single <mouseScrollSensitivity>k__BackingField`  
- `private System.Single <keyboardMoveSensitivity>k__BackingField`  
- `private System.Single <keyboardRotateSensitivity>k__BackingField`  
- `private System.Single <keyboardZoomSensitivity>k__BackingField`  
- `private System.Single <mouseMoveSensitivity>k__BackingField`  
- `private System.Single <mouseRotateSensitivity>k__BackingField`  
- `private System.Single <mouseZoomSensitivity>k__BackingField`  
- `private System.Boolean <mouseInvertX>k__BackingField`  
- `private System.Boolean <mouseInvertY>k__BackingField`  
- `private System.Single <gamepadMoveSensitivity>k__BackingField`  
- `private System.Single <gamepadRotateSensitivity>k__BackingField`  
- `private System.Single <gamepadZoomSensitivity>k__BackingField`  
- `private System.Boolean <gamepadInvertX>k__BackingField`  
- `private System.Boolean <gamepadInvertY>k__BackingField`  
- `public static const System.String kName`  
- `public static const System.String kMiscTab`  

## Properties

- `public System.Boolean elevationDraggingEnabled { get; set }`  
- `public System.Single mouseScrollSensitivity { get; set }`  
- `public System.Single finalScrollSensitivity { get }`  
- `public System.Single keyboardMoveSensitivity { get; set }`  
- `public System.Single keyboardRotateSensitivity { get; set }`  
- `public System.Single keyboardZoomSensitivity { get; set }`  
- `public System.Single mouseMoveSensitivity { get; set }`  
- `public System.Single mouseRotateSensitivity { get; set }`  
- `public System.Single mouseZoomSensitivity { get; set }`  
- `public System.Boolean mouseInvertX { get; set }`  
- `public System.Boolean mouseInvertY { get; set }`  
- `public System.Single gamepadMoveSensitivity { get; set }`  
- `public System.Single gamepadRotateSensitivity { get; set }`  
- `public System.Single gamepadZoomSensitivity { get; set }`  
- `public System.Boolean gamepadInvertX { get; set }`  
- `public System.Boolean gamepadInvertY { get; set }`  
- `private System.Boolean isKeyboardConflict { private get }`  
- `private System.Boolean isMouseConflict { private get }`  
- `private System.Boolean isGamepadConflict { private get }`  

## Constructors

- `public InputSettings()`  

## Methods

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  
- `private GetPageSection(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Input.InputManager+DeviceType device) : System.Void`  
- `private GetTabOrder() : System.String[]`  
- `public virtual SetDefaults() : System.Void`  
- `private SetDefaultsForDevice(Game.Input.InputManager+DeviceType device) : System.Void`  

## Nested types

- `Game.Settings.InputSettings+<>c`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_0`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_1`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_2`  

