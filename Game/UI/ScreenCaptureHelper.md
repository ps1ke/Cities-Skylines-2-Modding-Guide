# Game.UI.ScreenCaptureHelper

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ScreenCaptureHelper
{
    private static Colossal.Logging.ILog log;
    private static const System.String kOutlinesPassName;

    public static System.Void CaptureScreenshot(UnityEngine.Camera camera, UnityEngine.RenderTexture destination, Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings settings);
    public static UnityEngine.RenderTexture CreateRenderTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format);
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.String kOutlinesPassName`  

```csharp
private static const System.String kOutlinesPassName;
```


## Methods

- `public static CaptureScreenshot(UnityEngine.Camera camera, UnityEngine.RenderTexture destination, Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings settings) : System.Void`  

```csharp
public static System.Void CaptureScreenshot(UnityEngine.Camera camera, UnityEngine.RenderTexture destination, Game.UI.Menu.MenuHelpers+SaveGamePreviewSettings settings);
```

- `public static CreateRenderTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format = R8G8B8A8_UNorm) : UnityEngine.RenderTexture`  

```csharp
public static UnityEngine.RenderTexture CreateRenderTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format);
```


## Nested types

- `Game.UI.ScreenCaptureHelper+AsyncRequest`  

