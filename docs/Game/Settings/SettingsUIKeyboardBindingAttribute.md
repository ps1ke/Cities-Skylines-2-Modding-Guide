# Game.Settings.SettingsUIKeyboardBindingAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIKeybindingAttribute`  

**Attributes:** `Usage`  

## Fields

- `public readonly Game.Input.BindingKeyboard defaultKey`  
- `public readonly System.Boolean alt`  
- `public readonly System.Boolean ctrl`  
- `public readonly System.Boolean shift`  

## Properties

- `public System.String control { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> modifierControls { get }`  

## Constructors

- `public SettingsUIKeyboardBindingAttribute(System.String actionName = null)`  
- `public SettingsUIKeyboardBindingAttribute(Game.Input.AxisComponent component, System.String actionName = null)`  
- `public SettingsUIKeyboardBindingAttribute(Game.Input.Vector2Component component, System.String actionName = null)`  
- `public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  
- `public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  
- `public SettingsUIKeyboardBindingAttribute(Game.Input.BindingKeyboard defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  
- `public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  
- `public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  
- `public SettingsUIKeyboardBindingAttribute(UnityEngine.InputSystem.Key defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

## Nested types

- `Game.Settings.SettingsUIKeyboardBindingAttribute+<get_modifierControls>d__7`  

