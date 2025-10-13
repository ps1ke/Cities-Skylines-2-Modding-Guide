# Game.Settings.SettingsUIGamepadBindingAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIKeybindingAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIGamepadBindingAttribute : Game.Settings.SettingsUIKeybindingAttribute
{
    public readonly Game.Input.BindingGamepad defaultKey;
    public readonly System.Boolean leftStick;
    public readonly System.Boolean rightStick;

    public System.String control { get; }
    public System.Collections.Generic.IEnumerable<System.String> modifierControls { get; }

    public SettingsUIGamepadBindingAttribute(System.String actionName);
    public SettingsUIGamepadBindingAttribute(Game.Input.AxisComponent component, System.String actionName);
    public SettingsUIGamepadBindingAttribute(Game.Input.Vector2Component component, System.String actionName);
    public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, System.String actionName, System.Boolean leftStick, System.Boolean rightStick);
    public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean leftStick, System.Boolean rightStick);
    public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean leftStick, System.Boolean rightStick);
    public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, System.String actionName, System.Boolean leftStick);
    public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean leftStick);
    public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean leftStick);

}
```


## Fields

- `public readonly Game.Input.BindingGamepad defaultKey`  

```csharp
public readonly Game.Input.BindingGamepad defaultKey;
```

- `public readonly System.Boolean leftStick`  

```csharp
public readonly System.Boolean leftStick;
```

- `public readonly System.Boolean rightStick`  

```csharp
public readonly System.Boolean rightStick;
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

- `public SettingsUIGamepadBindingAttribute(System.String actionName = null)`  

```csharp
public SettingsUIGamepadBindingAttribute(System.String actionName);
```

- `public SettingsUIGamepadBindingAttribute(Game.Input.AxisComponent component, System.String actionName = null)`  

```csharp
public SettingsUIGamepadBindingAttribute(Game.Input.AxisComponent component, System.String actionName);
```

- `public SettingsUIGamepadBindingAttribute(Game.Input.Vector2Component component, System.String actionName = null)`  

```csharp
public SettingsUIGamepadBindingAttribute(Game.Input.Vector2Component component, System.String actionName);
```

- `public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, System.String actionName = null, System.Boolean leftStick = False, System.Boolean rightStick = False)`  

```csharp
public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, System.String actionName, System.Boolean leftStick, System.Boolean rightStick);
```

- `public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean leftStick = False, System.Boolean rightStick = False)`  

```csharp
public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean leftStick, System.Boolean rightStick);
```

- `public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean leftStick = False, System.Boolean rightStick = False)`  

```csharp
public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean leftStick, System.Boolean rightStick);
```

- `public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, System.String actionName = null, System.Boolean leftStick = False)`  

```csharp
public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, System.String actionName, System.Boolean leftStick);
```

- `public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean leftStick = False)`  

```csharp
public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean leftStick);
```

- `public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean leftStick = False)`  

```csharp
public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean leftStick);
```


## Nested types

- `Game.Settings.SettingsUIGamepadBindingAttribute+<get_modifierControls>d__6`  

