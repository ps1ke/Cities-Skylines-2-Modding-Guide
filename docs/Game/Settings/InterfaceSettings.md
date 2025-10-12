# Game.Settings.InterfaceSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIGroupOrder`  

## Fields

- `private System.String <locale>k__BackingField`  
- `private System.String <interfaceStyle>k__BackingField`  
- `private System.Single <interfaceTransparency>k__BackingField`  
- `private System.Boolean <interfaceScaling>k__BackingField`  
- `private System.Single <textScale>k__BackingField`  
- `private System.Boolean <unlockHighlightsEnabled>k__BackingField`  
- `private System.Boolean <chirperPopupsEnabled>k__BackingField`  
- `private System.Boolean <blockingPopupsEnabled>k__BackingField`  
- `private System.Boolean <showWhatsNewPanel>k__BackingField`  
- `private Game.Settings.InterfaceSettings+InputHintsType <inputHintsType>k__BackingField`  
- `private Game.Settings.InterfaceSettings+KeyboardLayout <keyboardLayout>k__BackingField`  
- `private System.Boolean <shortcutHints>k__BackingField`  
- `private Game.Settings.InterfaceSettings+TimeFormat <timeFormat>k__BackingField`  
- `private Game.Settings.InterfaceSettings+TemperatureUnit <temperatureUnit>k__BackingField`  
- `private Game.Settings.InterfaceSettings+UnitSystem <unitSystem>k__BackingField`  
- `private System.Collections.Generic.HashSet<System.String> <dismissedConfirmations>k__BackingField`  
- `public static const System.String kName`  
- `public static const System.String kLanguageGroup`  
- `public static const System.String kStyleGroup`  
- `public static const System.String kPopupGroup`  
- `public static const System.String kHintGroup`  
- `public static const System.String kUnitGroup`  
- `public static const System.String kBlockGroup`  

## Properties

- `public System.String currentLocale { get; set }`  
- `public System.String locale { get; set }`  
- `public System.String interfaceStyle { get; set }`  
- `public System.Single interfaceTransparency { get; set }`  
- `public System.Boolean interfaceScaling { get; set }`  
- `public System.Single textScale { get; set }`  
- `public System.Boolean unlockHighlightsEnabled { get; set }`  
- `public System.Boolean chirperPopupsEnabled { get; set }`  
- `public System.Boolean blockingPopupsEnabled { get; set }`  
- `public System.Boolean showWhatsNewPanel { get; set }`  
- `public System.Boolean resetDismissedConfirmations { set }`  
- `public Game.Settings.InterfaceSettings+InputHintsType inputHintsType { get; set }`  
- `public Game.Settings.InterfaceSettings+KeyboardLayout keyboardLayout { get; set }`  
- `public System.Boolean shortcutHints { get; set }`  
- `public Game.Settings.InterfaceSettings+TimeFormat timeFormat { get; set }`  
- `public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit { get; set }`  
- `public Game.Settings.InterfaceSettings+UnitSystem unitSystem { get; set }`  
- `public System.Collections.Generic.HashSet<System.String> dismissedConfirmations { get; set }`  

## Constructors

- `public InterfaceSettings()`  

## Methods

- `public AddDismissedConfirmation(System.String name) : System.Void`  
- `public virtual Apply() : System.Void`  
- `public GetFinalInputHintsType() : Game.Input.InputManager+GamepadType`  
- `public static GetInterfaceStyleValues() : Game.UI.Widgets.DropdownItem<System.String>[]`  
- `public static GetLanguageValues() : Game.UI.Widgets.DropdownItem<System.String>[]`  
- `public virtual SetDefaults() : System.Void`  

## Nested types

- `Game.Settings.InterfaceSettings+InputHintsType`  
- `Game.Settings.InterfaceSettings+KeyboardLayout`  
- `Game.Settings.InterfaceSettings+TimeFormat`  
- `Game.Settings.InterfaceSettings+TemperatureUnit`  
- `Game.Settings.InterfaceSettings+UnitSystem`  

