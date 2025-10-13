# Game.Settings.SharedSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SharedSettings
{
    private Game.Settings.GeneralSettings <general>k__BackingField;
    private Game.Settings.AudioSettings <audio>k__BackingField;
    private Game.Settings.GameplaySettings <gameplay>k__BackingField;
    private Game.Settings.RadioSettings <radio>k__BackingField;
    private Game.Settings.GraphicsSettings <graphics>k__BackingField;
    private Game.Settings.EditorSettings <editor>k__BackingField;
    private Game.Settings.InterfaceSettings <userInterface>k__BackingField;
    private Game.Settings.InputSettings <input>k__BackingField;
    private Game.Settings.KeybindingSettings <keybinding>k__BackingField;
    private Game.Settings.ModdingSettings <modding>k__BackingField;
    private Game.Settings.UserState <userState>k__BackingField;
    private readonly System.Collections.Generic.List<Game.Settings.Setting> m_Settings;

    public static Game.Settings.SharedSettings instance { get; }
    public Game.Settings.GeneralSettings general { get; private set; }
    public Game.Settings.AudioSettings audio { get; private set; }
    public Game.Settings.GameplaySettings gameplay { get; private set; }
    public Game.Settings.RadioSettings radio { get; private set; }
    public Game.Settings.GraphicsSettings graphics { get; private set; }
    public Game.Settings.EditorSettings editor { get; private set; }
    public Game.Settings.InterfaceSettings userInterface { get; private set; }
    public Game.Settings.InputSettings input { get; private set; }
    public Game.Settings.KeybindingSettings keybinding { get; private set; }
    public Game.Settings.ModdingSettings modding { get; private set; }
    public Game.Settings.UserState userState { get; private set; }

    public SharedSettings(Colossal.Localization.LocalizationManager localizationManager);

    private System.Void <RegisterInOptionsUI>g__OnControlSchemeChanged|48_2(Game.Input.InputManager+ControlScheme controlScheme);
    private System.Void <RegisterInOptionsUI>g__OnDeviceChange|48_1(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change);
    public System.Void Apply();
    public System.Void LoadSettings();
    public System.Void LoadUserSettings();
    public System.Void RegisterInOptionsUI();
    public System.Void Reset();
}
```


## Fields

- `private Game.Settings.GeneralSettings <general>k__BackingField`  

```csharp
private Game.Settings.GeneralSettings <general>k__BackingField;
```

- `private Game.Settings.AudioSettings <audio>k__BackingField`  

```csharp
private Game.Settings.AudioSettings <audio>k__BackingField;
```

- `private Game.Settings.GameplaySettings <gameplay>k__BackingField`  

```csharp
private Game.Settings.GameplaySettings <gameplay>k__BackingField;
```

- `private Game.Settings.RadioSettings <radio>k__BackingField`  

```csharp
private Game.Settings.RadioSettings <radio>k__BackingField;
```

- `private Game.Settings.GraphicsSettings <graphics>k__BackingField`  

```csharp
private Game.Settings.GraphicsSettings <graphics>k__BackingField;
```

- `private Game.Settings.EditorSettings <editor>k__BackingField`  

```csharp
private Game.Settings.EditorSettings <editor>k__BackingField;
```

- `private Game.Settings.InterfaceSettings <userInterface>k__BackingField`  

```csharp
private Game.Settings.InterfaceSettings <userInterface>k__BackingField;
```

- `private Game.Settings.InputSettings <input>k__BackingField`  

```csharp
private Game.Settings.InputSettings <input>k__BackingField;
```

- `private Game.Settings.KeybindingSettings <keybinding>k__BackingField`  

```csharp
private Game.Settings.KeybindingSettings <keybinding>k__BackingField;
```

- `private Game.Settings.ModdingSettings <modding>k__BackingField`  

```csharp
private Game.Settings.ModdingSettings <modding>k__BackingField;
```

- `private Game.Settings.UserState <userState>k__BackingField`  

```csharp
private Game.Settings.UserState <userState>k__BackingField;
```

- `private readonly System.Collections.Generic.List<Game.Settings.Setting> m_Settings`  

```csharp
private readonly System.Collections.Generic.List<Game.Settings.Setting> m_Settings;
```


## Properties

- `public static Game.Settings.SharedSettings instance { get }`  

```csharp
public static Game.Settings.SharedSettings instance { get; }
```

- `public Game.Settings.GeneralSettings general { get; private set }`  

```csharp
public Game.Settings.GeneralSettings general { get; private set; }
```

- `public Game.Settings.AudioSettings audio { get; private set }`  

```csharp
public Game.Settings.AudioSettings audio { get; private set; }
```

- `public Game.Settings.GameplaySettings gameplay { get; private set }`  

```csharp
public Game.Settings.GameplaySettings gameplay { get; private set; }
```

- `public Game.Settings.RadioSettings radio { get; private set }`  

```csharp
public Game.Settings.RadioSettings radio { get; private set; }
```

- `public Game.Settings.GraphicsSettings graphics { get; private set }`  

```csharp
public Game.Settings.GraphicsSettings graphics { get; private set; }
```

- `public Game.Settings.EditorSettings editor { get; private set }`  

```csharp
public Game.Settings.EditorSettings editor { get; private set; }
```

- `public Game.Settings.InterfaceSettings userInterface { get; private set }`  

```csharp
public Game.Settings.InterfaceSettings userInterface { get; private set; }
```

- `public Game.Settings.InputSettings input { get; private set }`  

```csharp
public Game.Settings.InputSettings input { get; private set; }
```

- `public Game.Settings.KeybindingSettings keybinding { get; private set }`  

```csharp
public Game.Settings.KeybindingSettings keybinding { get; private set; }
```

- `public Game.Settings.ModdingSettings modding { get; private set }`  

```csharp
public Game.Settings.ModdingSettings modding { get; private set; }
```

- `public Game.Settings.UserState userState { get; private set }`  

```csharp
public Game.Settings.UserState userState { get; private set; }
```


## Constructors

- `public SharedSettings(Colossal.Localization.LocalizationManager localizationManager)`  

```csharp
public SharedSettings(Colossal.Localization.LocalizationManager localizationManager);
```


## Methods

- `private <RegisterInOptionsUI>g__OnControlSchemeChanged|48_2(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
private System.Void <RegisterInOptionsUI>g__OnControlSchemeChanged|48_2(Game.Input.InputManager+ControlScheme controlScheme);
```

- `private <RegisterInOptionsUI>g__OnDeviceChange|48_1(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  

```csharp
private System.Void <RegisterInOptionsUI>g__OnDeviceChange|48_1(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change);
```

- `public Apply() : System.Void`  

```csharp
public System.Void Apply();
```

- `public LoadSettings() : System.Void`  

```csharp
public System.Void LoadSettings();
```

- `public LoadUserSettings() : System.Void`  

```csharp
public System.Void LoadUserSettings();
```

- `public RegisterInOptionsUI() : System.Void`  

```csharp
public System.Void RegisterInOptionsUI();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


## Nested types

- `Game.Settings.SharedSettings+<>c`  

