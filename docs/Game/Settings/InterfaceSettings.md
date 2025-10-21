# Game.Settings.InterfaceSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIGroupOrder`  

## Code

```csharp
public class InterfaceSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.String <locale>k__BackingField;
    private System.String <interfaceStyle>k__BackingField;
    private System.Single <interfaceTransparency>k__BackingField;
    private System.Boolean <interfaceScaling>k__BackingField;
    private System.Single <textScale>k__BackingField;
    private System.Boolean <unlockHighlightsEnabled>k__BackingField;
    private System.Boolean <chirperPopupsEnabled>k__BackingField;
    private System.Boolean <blockingPopupsEnabled>k__BackingField;
    private System.Boolean <showWhatsNewPanel>k__BackingField;
    private Game.Settings.InterfaceSettings+InputHintsType <inputHintsType>k__BackingField;
    private Game.Settings.InterfaceSettings+KeyboardLayout <keyboardLayout>k__BackingField;
    private System.Boolean <shortcutHints>k__BackingField;
    private Game.Settings.InterfaceSettings+TimeFormat <timeFormat>k__BackingField;
    private Game.Settings.InterfaceSettings+TemperatureUnit <temperatureUnit>k__BackingField;
    private Game.Settings.InterfaceSettings+UnitSystem <unitSystem>k__BackingField;
    private System.Collections.Generic.HashSet<System.String> <dismissedConfirmations>k__BackingField;
    public static const System.String kName;
    public static const System.String kLanguageGroup;
    public static const System.String kStyleGroup;
    public static const System.String kPopupGroup;
    public static const System.String kHintGroup;
    public static const System.String kUnitGroup;
    public static const System.String kBlockGroup;

    public System.String currentLocale { get; set; }
    public System.String locale { get; set; }
    public System.String interfaceStyle { get; set; }
    public System.Single interfaceTransparency { get; set; }
    public System.Boolean interfaceScaling { get; set; }
    public System.Single textScale { get; set; }
    public System.Boolean unlockHighlightsEnabled { get; set; }
    public System.Boolean chirperPopupsEnabled { get; set; }
    public System.Boolean blockingPopupsEnabled { get; set; }
    public System.Boolean showWhatsNewPanel { get; set; }
    public System.Boolean resetDismissedConfirmations { set; }
    public Game.Settings.InterfaceSettings+InputHintsType inputHintsType { get; set; }
    public Game.Settings.InterfaceSettings+KeyboardLayout keyboardLayout { get; set; }
    public System.Boolean shortcutHints { get; set; }
    public Game.Settings.InterfaceSettings+TimeFormat timeFormat { get; set; }
    public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit { get; set; }
    public Game.Settings.InterfaceSettings+UnitSystem unitSystem { get; set; }
    public System.Collections.Generic.HashSet<System.String> dismissedConfirmations { get; set; }

    public InterfaceSettings();

    public System.Void AddDismissedConfirmation(System.String name);
    public virtual System.Void Apply();
    public Game.Input.InputManager+GamepadType GetFinalInputHintsType();
    public static Game.UI.Widgets.DropdownItem<System.String>[] GetInterfaceStyleValues();
    public static Game.UI.Widgets.DropdownItem<System.String>[] GetLanguageValues();
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private System.String <locale>k__BackingField`  

```csharp
private System.String <locale>k__BackingField;
```

- `private System.String <interfaceStyle>k__BackingField`  

```csharp
private System.String <interfaceStyle>k__BackingField;
```

- `private System.Single <interfaceTransparency>k__BackingField`  

```csharp
private System.Single <interfaceTransparency>k__BackingField;
```

- `private System.Boolean <interfaceScaling>k__BackingField`  

```csharp
private System.Boolean <interfaceScaling>k__BackingField;
```

- `private System.Single <textScale>k__BackingField`  

```csharp
private System.Single <textScale>k__BackingField;
```

- `private System.Boolean <unlockHighlightsEnabled>k__BackingField`  

```csharp
private System.Boolean <unlockHighlightsEnabled>k__BackingField;
```

- `private System.Boolean <chirperPopupsEnabled>k__BackingField`  

```csharp
private System.Boolean <chirperPopupsEnabled>k__BackingField;
```

- `private System.Boolean <blockingPopupsEnabled>k__BackingField`  

```csharp
private System.Boolean <blockingPopupsEnabled>k__BackingField;
```

- `private System.Boolean <showWhatsNewPanel>k__BackingField`  

```csharp
private System.Boolean <showWhatsNewPanel>k__BackingField;
```

- `private Game.Settings.InterfaceSettings+InputHintsType <inputHintsType>k__BackingField`  

```csharp
private Game.Settings.InterfaceSettings+InputHintsType <inputHintsType>k__BackingField;
```

- `private Game.Settings.InterfaceSettings+KeyboardLayout <keyboardLayout>k__BackingField`  

```csharp
private Game.Settings.InterfaceSettings+KeyboardLayout <keyboardLayout>k__BackingField;
```

- `private System.Boolean <shortcutHints>k__BackingField`  

```csharp
private System.Boolean <shortcutHints>k__BackingField;
```

- `private Game.Settings.InterfaceSettings+TimeFormat <timeFormat>k__BackingField`  

```csharp
private Game.Settings.InterfaceSettings+TimeFormat <timeFormat>k__BackingField;
```

- `private Game.Settings.InterfaceSettings+TemperatureUnit <temperatureUnit>k__BackingField`  

```csharp
private Game.Settings.InterfaceSettings+TemperatureUnit <temperatureUnit>k__BackingField;
```

- `private Game.Settings.InterfaceSettings+UnitSystem <unitSystem>k__BackingField`  

```csharp
private Game.Settings.InterfaceSettings+UnitSystem <unitSystem>k__BackingField;
```

- `private System.Collections.Generic.HashSet<System.String> <dismissedConfirmations>k__BackingField`  

```csharp
private System.Collections.Generic.HashSet<System.String> <dismissedConfirmations>k__BackingField;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `public static const System.String kLanguageGroup`  

```csharp
public static const System.String kLanguageGroup;
```

- `public static const System.String kStyleGroup`  

```csharp
public static const System.String kStyleGroup;
```

- `public static const System.String kPopupGroup`  

```csharp
public static const System.String kPopupGroup;
```

- `public static const System.String kHintGroup`  

```csharp
public static const System.String kHintGroup;
```

- `public static const System.String kUnitGroup`  

```csharp
public static const System.String kUnitGroup;
```

- `public static const System.String kBlockGroup`  

```csharp
public static const System.String kBlockGroup;
```


## Properties

- `public System.String currentLocale { get; set }`  

```csharp
public System.String currentLocale { get; set; }
```

- `public System.String locale { get; set }`  

```csharp
public System.String locale { get; set; }
```

- `public System.String interfaceStyle { get; set }`  

```csharp
public System.String interfaceStyle { get; set; }
```

- `public System.Single interfaceTransparency { get; set }`  

```csharp
public System.Single interfaceTransparency { get; set; }
```

- `public System.Boolean interfaceScaling { get; set }`  

```csharp
public System.Boolean interfaceScaling { get; set; }
```

- `public System.Single textScale { get; set }`  

```csharp
public System.Single textScale { get; set; }
```

- `public System.Boolean unlockHighlightsEnabled { get; set }`  

```csharp
public System.Boolean unlockHighlightsEnabled { get; set; }
```

- `public System.Boolean chirperPopupsEnabled { get; set }`  

```csharp
public System.Boolean chirperPopupsEnabled { get; set; }
```

- `public System.Boolean blockingPopupsEnabled { get; set }`  

```csharp
public System.Boolean blockingPopupsEnabled { get; set; }
```

- `public System.Boolean showWhatsNewPanel { get; set }`  

```csharp
public System.Boolean showWhatsNewPanel { get; set; }
```

- `public System.Boolean resetDismissedConfirmations { set }`  

```csharp
public System.Boolean resetDismissedConfirmations { set; }
```

- `public Game.Settings.InterfaceSettings+InputHintsType inputHintsType { get; set }`  

```csharp
public Game.Settings.InterfaceSettings+InputHintsType inputHintsType { get; set; }
```

- `public Game.Settings.InterfaceSettings+KeyboardLayout keyboardLayout { get; set }`  

```csharp
public Game.Settings.InterfaceSettings+KeyboardLayout keyboardLayout { get; set; }
```

- `public System.Boolean shortcutHints { get; set }`  

```csharp
public System.Boolean shortcutHints { get; set; }
```

- `public Game.Settings.InterfaceSettings+TimeFormat timeFormat { get; set }`  

```csharp
public Game.Settings.InterfaceSettings+TimeFormat timeFormat { get; set; }
```

- `public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit { get; set }`  

```csharp
public Game.Settings.InterfaceSettings+TemperatureUnit temperatureUnit { get; set; }
```

- `public Game.Settings.InterfaceSettings+UnitSystem unitSystem { get; set }`  

```csharp
public Game.Settings.InterfaceSettings+UnitSystem unitSystem { get; set; }
```

- `public System.Collections.Generic.HashSet<System.String> dismissedConfirmations { get; set }`  

```csharp
public System.Collections.Generic.HashSet<System.String> dismissedConfirmations { get; set; }
```


## Constructors

- `public InterfaceSettings()`  

```csharp
public InterfaceSettings();
```


## Methods

- `public AddDismissedConfirmation(System.String name) : System.Void`  

```csharp
public System.Void AddDismissedConfirmation(System.String name);
```

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `public GetFinalInputHintsType() : Game.Input.InputManager+GamepadType`  

```csharp
public Game.Input.InputManager+GamepadType GetFinalInputHintsType();
```

- `public static GetInterfaceStyleValues() : Game.UI.Widgets.DropdownItem<System.String>[]`  

```csharp
public static Game.UI.Widgets.DropdownItem<System.String>[] GetInterfaceStyleValues();
```

- `public static GetLanguageValues() : Game.UI.Widgets.DropdownItem<System.String>[]`  

```csharp
public static Game.UI.Widgets.DropdownItem<System.String>[] GetLanguageValues();
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```


## Nested types

- `Game.Settings.InterfaceSettings+InputHintsType`  
- `Game.Settings.InterfaceSettings+KeyboardLayout`  
- `Game.Settings.InterfaceSettings+TimeFormat`  
- `Game.Settings.InterfaceSettings+TemperatureUnit`  
- `Game.Settings.InterfaceSettings+UnitSystem`  

