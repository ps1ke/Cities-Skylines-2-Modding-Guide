# Game.Modding.ModSetting

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class abstract public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public abstract class ModSetting : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private readonly Game.Modding.IMod <mod>k__BackingField;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <name>k__BackingField;
    private System.Boolean <keyBindingRegistered>k__BackingField;
    private System.Reflection.PropertyInfo[] m_keyBindingProperties;
    private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField;

    internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get; }
    internal Game.Modding.IMod mod { internal get; }
    private System.Boolean builtIn { private get; }
    public System.String id { get; }
    public System.String name { get; }
    public System.Boolean keyBindingRegistered { get; private set; }
    private System.Reflection.PropertyInfo[] keyBindingProperties { private get; }

    public ModSetting(Game.Modding.IMod mod);

    private Game.Input.ProxyBinding <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p);
    private System.Void ApplyKeyBindings();
    private Game.Input.ProxyBinding CreateBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, System.String control, System.Collections.Generic.IEnumerable<System.String> modifierControls);
    private Game.Input.ProxyBinding CreateMimicBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, Game.Input.ProxyBinding sourceBinding);
    private Game.Input.ProxyBinding GenerateBinding(System.Reflection.PropertyInfo property);
    public Game.Input.ProxyAction GetAction(System.String name);
    public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> GetActions();
    public System.String GetBindingKeyHintLocaleID(System.String actionName);
    public System.String GetBindingKeyLocaleID(System.String actionName);
    public System.String GetBindingKeyLocaleID(System.String actionName, Game.Input.AxisComponent component);
    public System.String GetBindingKeyLocaleID(System.String actionName, Game.Input.Vector2Component component);
    private System.String GetBindingKeyLocaleID(System.String actionName, System.String componentName);
    public System.String GetBindingMapLocaleID();
    public System.String GetEnumValueLocaleID<T>(T value);
    public System.String GetOptionDescLocaleID(System.String optionName);
    public System.String GetOptionFormatLocaleID(System.String optionName);
    public System.String GetOptionGroupLocaleID(System.String groupName);
    public System.String GetOptionLabelLocaleID(System.String optionName);
    public System.String GetOptionTabLocaleID(System.String tabName);
    public System.String GetOptionWarningLocaleID(System.String optionName);
    public System.String GetSettingsLocaleID();
    private System.Void InitializeKeyBindings();
    public System.Void RegisterInOptionsUI();
    public System.Void RegisterKeyBindings();
    protected System.Void ResetKeyBindings();
    private System.Boolean TryGetSourceBindingForMimic(System.Reflection.PropertyInfo property, Game.Input.InputManager+DeviceType device, Game.Input.ActionComponent component, Game.Input.ProxyBinding& sourceBinding);
    public System.Void UnregisterInOptionsUI();
}
```


## Fields

- `private readonly Game.Modding.IMod <mod>k__BackingField`  

```csharp
private readonly Game.Modding.IMod <mod>k__BackingField;
```

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
```

- `private System.Boolean <keyBindingRegistered>k__BackingField`  

```csharp
private System.Boolean <keyBindingRegistered>k__BackingField;
```

- `private System.Reflection.PropertyInfo[] m_keyBindingProperties`  

```csharp
private System.Reflection.PropertyInfo[] m_keyBindingProperties;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField;
```


## Properties

- `internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get }`  

```csharp
internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get; }
```

- `internal Game.Modding.IMod mod { internal get }`  

```csharp
internal Game.Modding.IMod mod { internal get; }
```

- `private System.Boolean builtIn { private get }`  

```csharp
private System.Boolean builtIn { private get; }
```

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean keyBindingRegistered { get; private set }`  

```csharp
public System.Boolean keyBindingRegistered { get; private set; }
```

- `private System.Reflection.PropertyInfo[] keyBindingProperties { private get }`  

```csharp
private System.Reflection.PropertyInfo[] keyBindingProperties { private get; }
```


## Constructors

- `public ModSetting(Game.Modding.IMod mod)`  

```csharp
public ModSetting(Game.Modding.IMod mod);
```


## Methods

- `private <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p) : Game.Input.ProxyBinding`  

```csharp
private Game.Input.ProxyBinding <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p);
```

- `private ApplyKeyBindings() : System.Void`  

```csharp
private System.Void ApplyKeyBindings();
```

- `private CreateBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, System.String control, System.Collections.Generic.IEnumerable<System.String> modifierControls) : Game.Input.ProxyBinding`  

```csharp
private Game.Input.ProxyBinding CreateBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, System.String control, System.Collections.Generic.IEnumerable<System.String> modifierControls);
```

- `private CreateMimicBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, Game.Input.ProxyBinding sourceBinding) : Game.Input.ProxyBinding`  

```csharp
private Game.Input.ProxyBinding CreateMimicBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, Game.Input.ProxyBinding sourceBinding);
```

- `private GenerateBinding(System.Reflection.PropertyInfo property) : Game.Input.ProxyBinding`  

```csharp
private Game.Input.ProxyBinding GenerateBinding(System.Reflection.PropertyInfo property);
```

- `public GetAction(System.String name) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction GetAction(System.String name);
```

- `public GetActions() : System.Collections.Generic.IEnumerable<Game.Input.ProxyAction>`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> GetActions();
```

- `public GetBindingKeyHintLocaleID(System.String actionName) : System.String`  

```csharp
public System.String GetBindingKeyHintLocaleID(System.String actionName);
```

- `public GetBindingKeyLocaleID(System.String actionName) : System.String`  

```csharp
public System.String GetBindingKeyLocaleID(System.String actionName);
```

- `public GetBindingKeyLocaleID(System.String actionName, Game.Input.AxisComponent component) : System.String`  

```csharp
public System.String GetBindingKeyLocaleID(System.String actionName, Game.Input.AxisComponent component);
```

- `public GetBindingKeyLocaleID(System.String actionName, Game.Input.Vector2Component component) : System.String`  

```csharp
public System.String GetBindingKeyLocaleID(System.String actionName, Game.Input.Vector2Component component);
```

- `private GetBindingKeyLocaleID(System.String actionName, System.String componentName) : System.String`  

```csharp
private System.String GetBindingKeyLocaleID(System.String actionName, System.String componentName);
```

- `public GetBindingMapLocaleID() : System.String`  

```csharp
public System.String GetBindingMapLocaleID();
```

- `public GetEnumValueLocaleID<T>(T value) : System.String`  

```csharp
public System.String GetEnumValueLocaleID<T>(T value);
```

- `public GetOptionDescLocaleID(System.String optionName) : System.String`  

```csharp
public System.String GetOptionDescLocaleID(System.String optionName);
```

- `public GetOptionFormatLocaleID(System.String optionName) : System.String`  

```csharp
public System.String GetOptionFormatLocaleID(System.String optionName);
```

- `public GetOptionGroupLocaleID(System.String groupName) : System.String`  

```csharp
public System.String GetOptionGroupLocaleID(System.String groupName);
```

- `public GetOptionLabelLocaleID(System.String optionName) : System.String`  

```csharp
public System.String GetOptionLabelLocaleID(System.String optionName);
```

- `public GetOptionTabLocaleID(System.String tabName) : System.String`  

```csharp
public System.String GetOptionTabLocaleID(System.String tabName);
```

- `public GetOptionWarningLocaleID(System.String optionName) : System.String`  

```csharp
public System.String GetOptionWarningLocaleID(System.String optionName);
```

- `public GetSettingsLocaleID() : System.String`  

```csharp
public System.String GetSettingsLocaleID();
```

- `private InitializeKeyBindings() : System.Void`  

```csharp
private System.Void InitializeKeyBindings();
```

- `public RegisterInOptionsUI() : System.Void`  

```csharp
public System.Void RegisterInOptionsUI();
```

- `public RegisterKeyBindings() : System.Void`  

```csharp
public System.Void RegisterKeyBindings();
```

- `protected ResetKeyBindings() : System.Void`  

```csharp
protected System.Void ResetKeyBindings();
```

- `private TryGetSourceBindingForMimic(System.Reflection.PropertyInfo property, Game.Input.InputManager+DeviceType device, Game.Input.ActionComponent component, Game.Input.ProxyBinding& sourceBinding) : System.Boolean`  

```csharp
private System.Boolean TryGetSourceBindingForMimic(System.Reflection.PropertyInfo property, Game.Input.InputManager+DeviceType device, Game.Input.ActionComponent component, Game.Input.ProxyBinding& sourceBinding);
```

- `public UnregisterInOptionsUI() : System.Void`  

```csharp
public System.Void UnregisterInOptionsUI();
```


## Nested types

- `Game.Modding.ModSetting+<>c`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_0`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_1`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_2`  
- `Game.Modding.ModSetting+<>c__DisplayClass28_0`  

