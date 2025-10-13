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
public static ScreenResolution[] GetAvailableResolutions(bool all)
	{
		if (!all)
		{
			return simpleResolutions;
		}
		return resolutions;
	}
```

- `public static GetClosestAvailable(Game.Settings.ScreenResolution sample, System.Boolean all) : Game.Settings.ScreenResolution`  

```csharp
public static ScreenResolution GetClosestAvailable(ScreenResolution sample, bool all)
	{
		ScreenResolution screenResolution = default(ScreenResolution);
		ScreenResolution[] availableResolutions = GetAvailableResolutions(all);
		for (int i = 0; i < availableResolutions.Length; i++)
		{
			ScreenResolution screenResolution2 = availableResolutions[i];
			if (Math.Abs(screenResolution2.width - sample.width) + Math.Abs(screenResolution2.height - sample.height) < Math.Abs(screenResolution.width - sample.width) + Math.Abs(screenResolution.height - sample.height))
			{
				screenResolution = screenResolution2;
			}
			else if (screenResolution2.width == screenResolution.width && screenResolution2.height == screenResolution.height)
			{
				RefreshRate refreshRate = screenResolution2.refreshRate;
				if (Math.Abs(refreshRate.value - sample.refreshRate.value) < Math.Abs(screenResolution.refreshRate.value - sample.refreshRate.value))
				{
					screenResolution = screenResolution2;
				}
			}
		}
		ScreenResolution result = ((screenResolution.width > 0 && screenResolution.height > 0) ? screenResolution : sample);
		result.Sanitize();
		return result;
	}
```

- `public static GetFullscreenMode(Game.Settings.DisplayMode displayMode) : UnityEngine.FullScreenMode`  

```csharp
public static FullScreenMode GetFullscreenMode(DisplayMode displayMode)
	{
		return displayMode switch
		{
			DisplayMode.Fullscreen => FullScreenMode.ExclusiveFullScreen, 
			DisplayMode.FullscreenWindow => FullScreenMode.FullScreenWindow, 
			DisplayMode.Window => FullScreenMode.Windowed, 
			_ => FullScreenMode.Windowed, 
		};
	}
```

- `public static HasMultipleDisplay() : System.Boolean`  

```csharp
public static bool HasMultipleDisplay()
	{
		m_DisplayInfos.Clear();
		Screen.GetDisplayLayout(m_DisplayInfos);
		return m_DisplayInfos.Count > 1;
	}
```

- `public static HideAdditionalResolutionOption() : System.Boolean`  

```csharp
public static bool HideAdditionalResolutionOption()
	{
		return simpleResolutions.Length == resolutions.Length;
	}
```

- `public static RebuildResolutions() : System.Void`  

```csharp
public static void RebuildResolutions()
	{
		resolutions = (from x in new List<ScreenResolution>(Screen.resolutions.Select((Resolution r) => new ScreenResolution(r)))
			orderby x.width descending, x.height descending, x.refreshRate.value descending
			select x).ToArray();
		simpleResolutions = (from r in resolutions
			group r by (width: r.width, height: r.height, refreshRate: (int)Math.Round(r.refreshRate.value)) into g
			select g.Aggregate(g.First(), (ScreenResolution a, ScreenResolution b) => (!(b.refreshRateDelta < a.refreshRateDelta)) ? a : b)).ToArray();
	}
```


## Nested types

- `Game.Settings.ScreenHelper+<>c`  

