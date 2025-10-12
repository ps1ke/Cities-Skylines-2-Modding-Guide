# Game.Settings.ScreenHelper

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static System.Collections.Generic.List<UnityEngine.DisplayInfo> m_DisplayInfos`  
- `private static Game.Settings.ScreenResolution[] <resolutions>k__BackingField`  
- `private static Game.Settings.ScreenResolution[] <simpleResolutions>k__BackingField`  

## Properties

- `public static Game.Settings.ScreenResolution currentResolution { get }`  
- `private static Game.Settings.ScreenResolution[] resolutions { private get; private set }`  
- `private static Game.Settings.ScreenResolution[] simpleResolutions { private get; private set }`  
- `public static Game.Settings.DisplayMode currentDisplayMode { get }`  

## Methods

- `public static GetAvailableResolutions(System.Boolean all) : Game.Settings.ScreenResolution[]`  
- `public static GetClosestAvailable(Game.Settings.ScreenResolution sample, System.Boolean all) : Game.Settings.ScreenResolution`  
- `public static GetFullscreenMode(Game.Settings.DisplayMode displayMode) : UnityEngine.FullScreenMode`  
- `public static HasMultipleDisplay() : System.Boolean`  
- `public static HideAdditionalResolutionOption() : System.Boolean`  
- `public static RebuildResolutions() : System.Void`  

## Nested types

- `Game.Settings.ScreenHelper+<>c`  

