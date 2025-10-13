# Game.Settings.SettingsUIMouseActionAttribute

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.SettingsUIInputActionAttribute`  

**Attributes:** `Usage`  

## Code

```csharp
public class SettingsUIMouseActionAttribute : Game.Settings.SettingsUIInputActionAttribute
{
    public SettingsUIMouseActionAttribute(System.String name, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, System.String[] usages, System.String[] interactions, System.String[] processors);
    public SettingsUIMouseActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages);
    public SettingsUIMouseActionAttribute(System.String name, System.String[] customUsages);

}
```


## Constructors

- `public SettingsUIMouseActionAttribute(System.String name, Game.Input.ActionType type = Button, System.Boolean allowModifiers = True, System.Boolean developerOnly = False, System.String[] usages = null, System.String[] interactions = null, System.String[] processors = null)`  

```csharp
public SettingsUIMouseActionAttribute(System.String name, Game.Input.ActionType type, System.Boolean allowModifiers, System.Boolean developerOnly, System.String[] usages, System.String[] interactions, System.String[] processors);
```

- `public SettingsUIMouseActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages)`  

```csharp
public SettingsUIMouseActionAttribute(System.String name, Game.Input.ActionType type, System.String[] customUsages);
```

- `public SettingsUIMouseActionAttribute(System.String name, System.String[] customUsages)`  

```csharp
public SettingsUIMouseActionAttribute(System.String name, System.String[] customUsages);
```


