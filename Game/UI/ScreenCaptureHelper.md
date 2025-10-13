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
public static void CaptureScreenshot(Camera camera, RenderTexture destination, MenuHelpers.SaveGamePreviewSettings settings)
	{
		if (!(destination == null) && !(camera == null))
		{
			HDRPDotsInputs.punctualLightsJobHandle.Complete();
			RenderPipelineSettings.ColorBufferFormat colorBufferFormat = (QualitySettings.GetRenderPipelineAssetAt(QualitySettings.GetQualityLevel()) as HDRenderPipelineAsset).currentPlatformRenderPipelineSettings.colorBufferFormat;
			RenderTexture renderTexture = new RenderTexture(destination.width, destination.height, 16, (GraphicsFormat)colorBufferFormat, 0);
			RenderingSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<RenderingSystem>();
			CustomPassCache.SetPassEnabled("Outlines Pass", enabled: false);
			UIManager.defaultUISystem.enabled = false;
			existingSystemManaged.hideOverlay = true;
			RenderTexture targetTexture = camera.targetTexture;
			camera.forceIntoRenderTexture = true;
			camera.targetTexture = renderTexture;
			for (int i = 0; i < 8; i++)
			{
				camera.Render();
			}
			camera.targetTexture = targetTexture;
			camera.forceIntoRenderTexture = false;
			existingSystemManaged.hideOverlay = false;
			UIManager.defaultUISystem.enabled = true;
			CustomPassCache.SetPassEnabled("Outlines Pass", enabled: true);
			Material material = new Material(Shader.Find("Hidden/ScreenCaptureCompose"));
			if (settings.stylized)
			{
				material.EnableKeyword("STYLIZE");
			}
			else
			{
				material.DisableKeyword("STYLIZE");
			}
			material.SetFloat("_Radius", settings.stylizedRadius);
			TextureAsset overlayImage = settings.overlayImage;
			if (overlayImage != null)
			{
				material.SetTexture("_Overlay", overlayImage.Load(0));
			}
			Graphics.Blit(renderTexture, destination, material, 0);
			if (overlayImage != null)
			{
				overlayImage.Unload();
			}
			Object.Destroy(material);
			destination.IncrementUpdateCount();
			Object.Destroy(renderTexture);
		}
	}
```

- `public static CreateRenderTarget(System.String name, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format = R8G8B8A8_UNorm) : UnityEngine.RenderTexture`  

```csharp
public static RenderTexture CreateRenderTarget(string name, int width, int height, GraphicsFormat format = GraphicsFormat.R8G8B8A8_UNorm)
	{
		RenderTexture renderTexture = new RenderTexture(width, height, 0, format, 0);
		renderTexture.name = name;
		renderTexture.hideFlags = HideFlags.HideAndDontSave;
		renderTexture.Create();
		return renderTexture;
	}
```


## Nested types

- `Game.UI.ScreenCaptureHelper+AsyncRequest`  

