# Game.Settings.SettingsUIGamepadActionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIInputActionAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIGamepadActionAttribute : Game.Settings.SettingsUIInputActionAttribute
{
    public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, Game.Input.Mode mode, System.String[] usages, System.String[] interactions, System.String[] processors);
    public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages);
    public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages);
    public SettingsUIGamepadActionAttribute(System.String name, Game.Input.Mode mode, System.String[] customUsages);
    public SettingsUIGamepadActionAttribute(System.String name, System.String[] customUsages);

}
```


## Constructors

- `public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type = Button, System.Boolean allowModifiers = True, System.Boolean developerOnly = False, Game.Input.Mode mode = Analog, System.String[] usages = null, System.String[] interactions = null, System.String[] processors = null)`  

```csharp
public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, Game.Input.Mode mode, System.String[] usages, System.String[] interactions, System.String[] processors);
```

- `public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages)`  

```csharp
public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages);
```

- `public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages)`  

```csharp
public SettingsUIGamepadActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages);
```

- `public SettingsUIGamepadActionAttribute(System.String name, Game.Input.Mode mode, System.String[] customUsages)`  

```csharp
public SettingsUIGamepadActionAttribute(System.String name, Game.Input.Mode mode, System.String[] customUsages);
```

- `public SettingsUIGamepadActionAttribute(System.String name, System.String[] customUsages)`  

```csharp
public SettingsUIGamepadActionAttribute(System.String name, System.String[] customUsages);
```


