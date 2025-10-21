# Game.PSI.PdxSdk.LauncherSettings

**Assembly:** `Game`  
**Namespace:** `Game.PSI.PdxSdk`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class LauncherSettings
{
    private static readonly System.String kLauncherSettingsFileName;
    private static readonly System.String kLauncherSettingsPath;
    private static Colossal.Logging.ILog log;

    public static System.Void LoadSettings(Colossal.Localization.LocalizationManager localizationManager, Game.Settings.SharedSettings gameSettings);
    public static System.Void SaveSettings(Game.Settings.SharedSettings gameSettings);
    private static System.Boolean TryGetLauncherSettings(Game.PSI.PdxSdk.LauncherSettings+Settings& launcherSettings);
}
```


## Fields

- `private static readonly System.String kLauncherSettingsFileName`  

```csharp
private static readonly System.String kLauncherSettingsFileName;
```

- `private static readonly System.String kLauncherSettingsPath`  

```csharp
private static readonly System.String kLauncherSettingsPath;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Methods

- `public static LoadSettings(Colossal.Localization.LocalizationManager localizationManager, Game.Settings.SharedSettings gameSettings) : System.Void`  

```csharp
public static System.Void LoadSettings(Colossal.Localization.LocalizationManager localizationManager, Game.Settings.SharedSettings gameSettings);
```

- `public static SaveSettings(Game.Settings.SharedSettings gameSettings) : System.Void`  

```csharp
public static System.Void SaveSettings(Game.Settings.SharedSettings gameSettings);
```

- `private static TryGetLauncherSettings(Game.PSI.PdxSdk.LauncherSettings+Settings& launcherSettings) : System.Boolean`  

```csharp
private static System.Boolean TryGetLauncherSettings(Game.PSI.PdxSdk.LauncherSettings+Settings& launcherSettings);
```


## Nested types

- `Game.PSI.PdxSdk.LauncherSettings+Settings`  

