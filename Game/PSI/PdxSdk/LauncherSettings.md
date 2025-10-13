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
public static void LoadSettings(LocalizationManager localizationManager, SharedSettings gameSettings)
	{
		if (TryGetLauncherSettings(out var launcherSettings))
		{
			launcherSettings.Apply(localizationManager, gameSettings);
		}
	}
```

- `public static SaveSettings(Game.Settings.SharedSettings gameSettings) : System.Void`  

```csharp
public static void SaveSettings(SharedSettings gameSettings)
	{
		if (TryGetLauncherSettings(out var launcherSettings))
		{
			try
			{
				launcherSettings.Merge(gameSettings);
				string contents = JSON.Dump(launcherSettings);
				File.WriteAllText(kLauncherSettingsPath, contents);
				log.Info("Launcher settings saved successfully");
			}
			catch (Exception p)
			{
				log.InfoFormat("Saving launcher settings failed: {0}", p);
			}
		}
	}
```

- `private static TryGetLauncherSettings(Game.PSI.PdxSdk.LauncherSettings+Settings& launcherSettings) : System.Boolean`  

```csharp
private static bool TryGetLauncherSettings(out Settings launcherSettings)
	{
		if (File.Exists(kLauncherSettingsPath))
		{
			try
			{
				Variant variant = JSON.Load(File.ReadAllText(kLauncherSettingsPath));
				launcherSettings = variant.Make<Settings>();
				log.Info("Loaded launcher settings successfully");
				return true;
			}
			catch (Exception p)
			{
				log.InfoFormat("Loading launcher settings failed: {0}", p);
			}
		}
		else
		{
			log.Info("Launcher settings not present");
		}
		launcherSettings = default(Settings);
		return false;
	}
```


## Nested types

- `Game.PSI.PdxSdk.LauncherSettings+Settings`  

