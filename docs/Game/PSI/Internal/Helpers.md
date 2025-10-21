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
public static System.Int32 AsInt(System.Boolean value);
```

- `public static GetSystemLanguage() : System.String`  

```csharp
public static System.String GetSystemLanguage();
```

- `public static ToTelemetry(Game.Settings.DisplayMode mode) : Game.PSI.Internal.Helpers+json_displaymode`  

```csharp
public static Game.PSI.Internal.Helpers+json_displaymode ToTelemetry(Game.Settings.DisplayMode mode);
```

- `public static ToTelemetry(Game.Settings.ScreenResolution resolution) : System.String`  

```csharp
public static System.String ToTelemetry(Game.Settings.ScreenResolution resolution);
```

- `public static ToTelemetry(Game.GameMode gameMode) : Game.PSI.Internal.Helpers+json_gameplay_mode`  

```csharp
public static Game.PSI.Internal.Helpers+json_gameplay_mode ToTelemetry(Game.GameMode gameMode);
```


## Nested types

- `Game.PSI.Internal.Helpers+json_displaymode`  
- `Game.PSI.Internal.Helpers+json_gameplay_mode`  

