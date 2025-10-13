# Game.Settings.ScreenHelper

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ScreenHelper
{
    private static System.Collections.Generic.List<UnityEngine.DisplayInfo> m_DisplayInfos;
    private static Game.Settings.ScreenResolution[] <resolutions>k__BackingField;
    private static Game.Settings.ScreenResolution[] <simpleResolutions>k__BackingField;

    public static Game.Settings.ScreenResolution currentResolution { get; }
    private static Game.Settings.ScreenResolution[] resolutions { private get; private set; }
    private static Game.Settings.ScreenResolution[] simpleResolutions { private get; private set; }
    public static Game.Settings.DisplayMode currentDisplayMode { get; }

    public static Game.Settings.ScreenResolution[] GetAvailableResolutions(System.Boolean all);
    public static Game.Settings.ScreenResolution GetClosestAvailable(Game.Settings.ScreenResolution sample, System.Boolean all);
    public static UnityEngine.FullScreenMode GetFullscreenMode(Game.Settings.DisplayMode displayMode);
    public static System.Boolean HasMultipleDisplay();
    public static System.Boolean HideAdditionalResolutionOption();
    public static System.Void RebuildResolutions();
}
```


## Fields

- `private static System.Collections.Generic.List<UnityEngine.DisplayInfo> m_DisplayInfos`  

```csharp
private static System.Collections.Generic.List<UnityEngine.DisplayInfo> m_DisplayInfos;
```

- `private static Game.Settings.ScreenResolution[] <resolutions>k__BackingField`  

```csharp
private static Game.Settings.ScreenResolution[] <resolutions>k__BackingField;
```

- `private static Game.Settings.ScreenResolution[] <simpleResolutions>k__BackingField`  

```csharp
private static Game.Settings.ScreenResolution[] <simpleResolutions>k__BackingField;
```


## Properties

- `public static Game.Settings.ScreenResolution currentResolution { get }`  

```csharp
public static Game.Settings.ScreenResolution currentResolution { get; }
```

- `private static Game.Settings.ScreenResolution[] resolutions { private get; private set }`  

```csharp
private static Game.Settings.ScreenResolution[] resolutions { private get; private set; }
```

- `private static Game.Settings.ScreenResolution[] simpleResolutions { private get; private set }`  

```csharp
private static Game.Settings.ScreenResolution[] simpleResolutions { private get; private set; }
```

- `public static Game.Settings.DisplayMode currentDisplayMode { get }`  

```csharp
public static Game.Settings.DisplayMode currentDisplayMode { get; }
```


## Methods

- `public static GetAvailableResolutions(System.Boolean all) : Game.Settings.ScreenResolution[]`  

```csharp
public static Game.Settings.ScreenResolution[] GetAvailableResolutions(System.Boolean all);
```

- `public static GetClosestAvailable(Game.Settings.ScreenResolution sample, System.Boolean all) : Game.Settings.ScreenResolution`  

```csharp
public static Game.Settings.ScreenResolution GetClosestAvailable(Game.Settings.ScreenResolution sample, System.Boolean all);
```

- `public static GetFullscreenMode(Game.Settings.DisplayMode displayMode) : UnityEngine.FullScreenMode`  

```csharp
public static UnityEngine.FullScreenMode GetFullscreenMode(Game.Settings.DisplayMode displayMode);
```

- `public static HasMultipleDisplay() : System.Boolean`  

```csharp
public static System.Boolean HasMultipleDisplay();
```

- `public static HideAdditionalResolutionOption() : System.Boolean`  

```csharp
public static System.Boolean HideAdditionalResolutionOption();
```

- `public static RebuildResolutions() : System.Void`  

```csharp
public static System.Void RebuildResolutions();
```


## Nested types

- `Game.Settings.ScreenHelper+<>c`  

