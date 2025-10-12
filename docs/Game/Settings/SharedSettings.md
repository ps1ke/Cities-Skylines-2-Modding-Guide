# Game.Settings.SharedSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Game.Settings.GeneralSettings <general>k__BackingField`  
- `private Game.Settings.AudioSettings <audio>k__BackingField`  
- `private Game.Settings.GameplaySettings <gameplay>k__BackingField`  
- `private Game.Settings.RadioSettings <radio>k__BackingField`  
- `private Game.Settings.GraphicsSettings <graphics>k__BackingField`  
- `private Game.Settings.EditorSettings <editor>k__BackingField`  
- `private Game.Settings.InterfaceSettings <userInterface>k__BackingField`  
- `private Game.Settings.InputSettings <input>k__BackingField`  
- `private Game.Settings.KeybindingSettings <keybinding>k__BackingField`  
- `private Game.Settings.ModdingSettings <modding>k__BackingField`  
- `private Game.Settings.UserState <userState>k__BackingField`  
- `private readonly System.Collections.Generic.List<Game.Settings.Setting> m_Settings`  

## Properties

- `public static Game.Settings.SharedSettings instance { get }`  
- `public Game.Settings.GeneralSettings general { get; private set }`  
- `public Game.Settings.AudioSettings audio { get; private set }`  
- `public Game.Settings.GameplaySettings gameplay { get; private set }`  
- `public Game.Settings.RadioSettings radio { get; private set }`  
- `public Game.Settings.GraphicsSettings graphics { get; private set }`  
- `public Game.Settings.EditorSettings editor { get; private set }`  
- `public Game.Settings.InterfaceSettings userInterface { get; private set }`  
- `public Game.Settings.InputSettings input { get; private set }`  
- `public Game.Settings.KeybindingSettings keybinding { get; private set }`  
- `public Game.Settings.ModdingSettings modding { get; private set }`  
- `public Game.Settings.UserState userState { get; private set }`  

## Constructors

- `public SharedSettings(Colossal.Localization.LocalizationManager localizationManager)`  

## Methods

- `private <RegisterInOptionsUI>g__OnControlSchemeChanged|48_2(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  
- `private <RegisterInOptionsUI>g__OnDeviceChange|48_1(UnityEngine.InputSystem.InputDevice changedDevice, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  
- `public Apply() : System.Void`  
- `public LoadSettings() : System.Void`  
- `public LoadUserSettings() : System.Void`  
- `public RegisterInOptionsUI() : System.Void`  
- `public Reset() : System.Void`  

## Nested types

- `Game.Settings.SharedSettings+<>c`  

