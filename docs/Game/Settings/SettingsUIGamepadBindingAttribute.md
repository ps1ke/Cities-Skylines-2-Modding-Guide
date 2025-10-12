# Game.Settings.SettingsUIGamepadBindingAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIKeybindingAttribute`  

**Attributes:** `Usage`  

## Fields

- `public readonly Game.Input.BindingGamepad defaultKey`  
- `public readonly System.Boolean leftStick`  
- `public readonly System.Boolean rightStick`  

## Properties

- `public System.String control { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> modifierControls { get }`  

## Constructors

- `public SettingsUIGamepadBindingAttribute(System.String actionName = null)`  
- `public SettingsUIGamepadBindingAttribute(Game.Input.AxisComponent component, System.String actionName = null)`  
- `public SettingsUIGamepadBindingAttribute(Game.Input.Vector2Component component, System.String actionName = null)`  
- `public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, System.String actionName = null, System.Boolean leftStick = False, System.Boolean rightStick = False)`  
- `public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean leftStick = False, System.Boolean rightStick = False)`  
- `public SettingsUIGamepadBindingAttribute(Game.Input.BindingGamepad defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean leftStick = False, System.Boolean rightStick = False)`  
- `public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, System.String actionName = null, System.Boolean leftStick = False)`  
- `public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean leftStick = False)`  
- `public SettingsUIGamepadBindingAttribute(UnityEngine.InputSystem.LowLevel.GamepadButton defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean leftStick = False)`  

## Nested types

- `Game.Settings.SettingsUIGamepadBindingAttribute+<get_modifierControls>d__6`  

