# Game.PSI.Internal.Helpers

**Assembly:** `Game`  
**Namespace:** `Game.PSI.Internal`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class Helpers
{
    private static readonly System.Collections.Generic.IReadOnlyDictionary<UnityEngine.SystemLanguage, System.String> s_SystemLanguageToISO;

    public static System.Int32 AsInt(System.Boolean value);
    public static System.String GetSystemLanguage();
    public static Game.PSI.Internal.Helpers+json_displaymode ToTelemetry(Game.Settings.DisplayMode mode);
    public static System.String ToTelemetry(Game.Settings.ScreenResolution resolution);
    public static Game.PSI.Internal.Helpers+json_gameplay_mode ToTelemetry(Game.GameMode gameMode);
}
```


## Fields

- `private static readonly System.Collections.Generic.IReadOnlyDictionary<UnityEngine.SystemLanguage, System.String> s_SystemLanguageToISO`  

```csharp
private static readonly System.Collections.Generic.IReadOnlyDictionary<UnityEngine.SystemLanguage, System.String> s_SystemLanguageToISO;
```


## Methods

- `public static AsInt(System.Boolean value) : System.Int32`  

```csharp
public static int AsInt(this bool value)
	{
		if (!value)
		{
			return 0;
		}
		return 1;
	}
```

- `public static GetSystemLanguage() : System.String`  

```csharp
public static string GetSystemLanguage()
	{
		if (s_SystemLanguageToISO.TryGetValue(Application.systemLanguage, out var value))
		{
			return value;
		}
		return string.Empty;
	}
```

- `public static ToTelemetry(Game.Settings.DisplayMode mode) : Game.PSI.Internal.Helpers+json_displaymode`  

```csharp
public static json_gameplay_mode ToTelemetry(this GameMode gameMode)
	{
		return gameMode switch
		{
			GameMode.Game => json_gameplay_mode.sandbox, 
			GameMode.Editor => json_gameplay_mode.editor, 
			_ => throw new TelemetryException($"Invalid game mode {gameMode}"), 
		};
	}
```

- `public static ToTelemetry(Game.Settings.ScreenResolution resolution) : System.String`  

```csharp
public static json_gameplay_mode ToTelemetry(this GameMode gameMode)
	{
		return gameMode switch
		{
			GameMode.Game => json_gameplay_mode.sandbox, 
			GameMode.Editor => json_gameplay_mode.editor, 
			_ => throw new TelemetryException($"Invalid game mode {gameMode}"), 
		};
	}
```

- `public static ToTelemetry(Game.GameMode gameMode) : Game.PSI.Internal.Helpers+json_gameplay_mode`  

```csharp
public static json_gameplay_mode ToTelemetry(this GameMode gameMode)
	{
		return gameMode switch
		{
			GameMode.Game => json_gameplay_mode.sandbox, 
			GameMode.Editor => json_gameplay_mode.editor, 
			_ => throw new TelemetryException($"Invalid game mode {gameMode}"), 
		};
	}
```


## Nested types

- `Game.PSI.Internal.Helpers+json_displaymode`  
- `Game.PSI.Internal.Helpers+json_gameplay_mode`  

