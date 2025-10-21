# Game.Settings.SettingsUIKeybindingAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class abstract public  

**Base:** `System.Attribute`  

## Code

```csharp
public abstract class SettingsUIKeybindingAttribute : System.Attribute
{
    public readonly System.String actionName;
    public readonly Game.Input.InputManager+DeviceType device;
    public readonly Game.Input.ActionType type;
    public readonly Game.Input.ActionComponent component;

    public System.String control { get; }
    public System.Collections.Generic.IEnumerable<System.String> modifierControls { get; }

    protected SettingsUIKeybindingAttribute(System.String actionName, Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.ActionComponent component);

}
```


## Fields

- `public readonly System.String actionName`  

```csharp
public readonly System.String actionName;
```

- `public readonly Game.Input.InputManager+DeviceType device`  

```csharp
public readonly Game.Input.InputManager+DeviceType device;
```

- `public readonly Game.Input.ActionType type`  

```csharp
public readonly Game.Input.ActionType type;
```

- `public readonly Game.Input.ActionComponent component`  

```csharp
public readonly Game.Input.ActionComponent component;
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

- `protected SettingsUIKeybindingAttribute(System.String actionName, Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.ActionComponent component)`  

```csharp
protected SettingsUIKeybindingAttribute(System.String actionName, Game.Input.InputManager+DeviceType device, Game.Input.ActionType type, Game.Input.ActionComponent component);
```


