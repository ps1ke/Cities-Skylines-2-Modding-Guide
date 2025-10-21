# Game.Settings.SettingsUIKeyboardActionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIInputActionAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIKeyboardActionAttribute : Game.Settings.SettingsUIInputActionAttribute
{
    public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, Game.Input.Mode mode, System.String[] usages, System.String[] interactions, System.String[] processors);
    public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages);
    public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages);
    public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.Mode mode, System.String[] customUsages);
    public SettingsUIKeyboardActionAttribute(System.String name, System.String[] customUsages);

}
```


## Constructors

- `public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type = Button, System.Boolean allowModifiers = True, System.Boolean developerOnly = False, Game.Input.Mode mode = DigitalNormalized, System.String[] usages = null, System.String[] interactions = null, System.String[] processors = null)`  

```csharp
public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, Game.Input.Mode mode, System.String[] usages, System.String[] interactions, System.String[] processors);
```

- `public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages)`  

```csharp
public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, Game.Input.Mode mode, System.String[] customUsages);
```

- `public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages)`  

```csharp
public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages);
```

- `public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.Mode mode, System.String[] customUsages)`  

```csharp
public SettingsUIKeyboardActionAttribute(System.String name, Game.Input.Mode mode, System.String[] customUsages);
```

- `public SettingsUIKeyboardActionAttribute(System.String name, System.String[] customUsages)`  

```csharp
public SettingsUIKeyboardActionAttribute(System.String name, System.String[] customUsages);
```


