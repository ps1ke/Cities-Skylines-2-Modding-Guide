# Game.Modding.ModSetting

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class abstract public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Fields

- `private readonly Game.Modding.IMod <mod>k__BackingField`  
- `private readonly System.String <id>k__BackingField`  
- `private readonly System.String <name>k__BackingField`  
- `private System.Boolean <keyBindingRegistered>k__BackingField`  
- `private System.Reflection.PropertyInfo[] m_keyBindingProperties`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField`  

## Properties

- `internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get }`  
- `internal Game.Modding.IMod mod { internal get }`  
- `private System.Boolean builtIn { private get }`  
- `public System.String id { get }`  
- `public System.String name { get }`  
- `public System.Boolean keyBindingRegistered { get; private set }`  
- `private System.Reflection.PropertyInfo[] keyBindingProperties { private get }`  

## Constructors

- `public ModSetting(Game.Modding.IMod mod)`  

## Methods

- `private <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p) : Game.Input.ProxyBinding`  
- `private ApplyKeyBindings() : System.Void`  
- `private CreateBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, System.String control, System.Collections.Generic.IEnumerable<System.String> modifierControls) : Game.Input.ProxyBinding`  
- `private CreateMimicBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, Game.Input.ProxyBinding sourceBinding) : Game.Input.ProxyBinding`  
- `private GenerateBinding(System.Reflection.PropertyInfo property) : Game.Input.ProxyBinding`  
- `public GetAction(System.String name) : Game.Input.ProxyAction`  
- `public GetActions() : System.Collections.Generic.IEnumerable<Game.Input.ProxyAction>`  
- `public GetBindingKeyHintLocaleID(System.String actionName) : System.String`  
- `public GetBindingKeyLocaleID(System.String actionName) : System.String`  
- `public GetBindingKeyLocaleID(System.String actionName, Game.Input.AxisComponent component) : System.String`  
- `public GetBindingKeyLocaleID(System.String actionName, Game.Input.Vector2Component component) : System.String`  
- `private GetBindingKeyLocaleID(System.String actionName, System.String componentName) : System.String`  
- `public GetBindingMapLocaleID() : System.String`  
- `public GetEnumValueLocaleID<T>(T value) : System.String`  
- `public GetOptionDescLocaleID(System.String optionName) : System.String`  
- `public GetOptionFormatLocaleID(System.String optionName) : System.String`  
- `public GetOptionGroupLocaleID(System.String groupName) : System.String`  
- `public GetOptionLabelLocaleID(System.String optionName) : System.String`  
- `public GetOptionTabLocaleID(System.String tabName) : System.String`  
- `public GetOptionWarningLocaleID(System.String optionName) : System.String`  
- `public GetSettingsLocaleID() : System.String`  
- `private InitializeKeyBindings() : System.Void`  
- `public RegisterInOptionsUI() : System.Void`  
- `public RegisterKeyBindings() : System.Void`  
- `protected ResetKeyBindings() : System.Void`  
- `private TryGetSourceBindingForMimic(System.Reflection.PropertyInfo property, Game.Input.InputManager+DeviceType device, Game.Input.ActionComponent component, Game.Input.ProxyBinding& sourceBinding) : System.Boolean`  
- `public UnregisterInOptionsUI() : System.Void`  

## Nested types

- `Game.Modding.ModSetting+<>c`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_0`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_1`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_2`  
- `Game.Modding.ModSetting+<>c__DisplayClass28_0`  

