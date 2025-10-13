# Game.Settings.SettingsUIMouseBindingAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIKeybindingAttribute`  

## Code

```csharp
public class SettingsUIMouseBindingAttribute : Game.Settings.SettingsUIKeybindingAttribute
{
    public readonly Game.Input.BindingMouse defaultKey;
    public readonly System.Boolean alt;
    public readonly System.Boolean ctrl;
    public readonly System.Boolean shift;

    public System.String control { get; }
    public System.Collections.Generic.IEnumerable<System.String> modifierControls { get; }

    public SettingsUIMouseBindingAttribute(System.String actionName);
    public SettingsUIMouseBindingAttribute(Game.Input.AxisComponent component, System.String actionName);
    public SettingsUIMouseBindingAttribute(Game.Input.Vector2Component component, System.String actionName);
    public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
    public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);

}
```


## Fields

- `public readonly Game.Input.BindingMouse defaultKey`  

```csharp
public readonly Game.Input.BindingMouse defaultKey;
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

- `public SettingsUIMouseBindingAttribute(System.String actionName = null)`  

```csharp
public SettingsUIMouseBindingAttribute(System.String actionName);
```

- `public SettingsUIMouseBindingAttribute(Game.Input.AxisComponent component, System.String actionName = null)`  

```csharp
public SettingsUIMouseBindingAttribute(Game.Input.AxisComponent component, System.String actionName);
```

- `public SettingsUIMouseBindingAttribute(Game.Input.Vector2Component component, System.String actionName = null)`  

```csharp
public SettingsUIMouseBindingAttribute(Game.Input.Vector2Component component, System.String actionName);
```

- `public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, Game.Input.AxisComponent component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, Game.Input.AxisComponent component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```

- `public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, Game.Input.Vector2Component component, System.String actionName = null, System.Boolean alt = False, System.Boolean ctrl = False, System.Boolean shift = False)`  

```csharp
public SettingsUIMouseBindingAttribute(Game.Input.BindingMouse defaultKey, Game.Input.Vector2Component component, System.String actionName, System.Boolean alt, System.Boolean ctrl, System.Boolean shift);
```


## Nested types

- `Game.Settings.SettingsUIMouseBindingAttribute+<get_modifierControls>d__7`  

