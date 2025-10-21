# Game.Settings.SettingsUIKeyboardBindingAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIKeybindingAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIKeyboardBindingAttribute : Game.Settings.SettingsUIKeybindingAttribute
{
    public readonly Game.Input.BindingKeyboard defaultKey;
    public readonly System.Boolean alt;
    public readonly System.Boolean ctrl;
    public readonly System.Boolean shift;

    public System.String control { get; }
    public System.Collections.Generic.IEnumerable<System.String> modifierControls { get; }

    public SettingsUIKeyboardBindingAttribute(System.String actionName);
    public SettingsUIKeyboardBindingAttribute(Game.Input.AxisComponent component, System.String actionName);
    public SettingsUIKeyboardBindingAttribute(Game.Input.Vector2Component component, System.String actionName);
    public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);

}
```


## Fields

- `public readonly Game.Input.BindingKeyboard defaultKey`  

```csharp
public readonly Game.Input.BindingKeyboard defaultKey;
```

- `public readonly System.Boolean alt`  

```csharp
public readonly System.Boolean alt;
```

- `public readonly System.Boolean ctrl`  

```csharp
public readonly System.Boolean ctrl;
```

- `public readonly System.Boolean shift`  

```csharp
public readonly System.Boolean shift;
```


## Properties

- `public System.String control { get }`  

```csharp
public System.String control { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> modifierControls { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modifierControls { get; }
```


## Constructors

- `public SettingsUIKeyboardBindingAttribute(System.String actionName = null)`  

```csharp
public SettingsUIKeyboardBindingAttribute(System.String actionName);
```

- `public SettingsUIKeyboardBindingAttribute(Game.Input.AxisComponent component, System.String actionName = null)`  

```csharp
public SettingsUIKeyboardBindingAttribute(Game.Input.AxisComponent component, System.String actionName);
```

- `public SettingsUIKeyboardBindingAttribute(Game.Input.Vector2Component component, System.String actionName = null)`  

```csharp
public SettingsUIKeyboardBindingAttribute(Game.Input.Vector2Component component, System.String actionName);
```

- `public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```


## Nested types

- `Game.Settings.SettingsUIKeyboardBindingAttribute+<get_modifierControls>d__7`  

