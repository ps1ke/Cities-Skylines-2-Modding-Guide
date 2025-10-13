# Game.Debug.ThumbnailsDebugUI

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `DebugContainer`  

## Code

```csharp
public static class ThumbnailsDebugUI
{
    private static System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildThumbnailsDebugUI();
}
```


## Methods

- `private static BuildThumbnailsDebugUI() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
private static List<DebugUI.Widget> BuildThumbnailsDebugUI()
	{
		ThumbnailCache tc = GameManager.instance?.thumbnailCache;
		if (tc != null)
		{
			new DebugUI.Foldout().displayName = "Thumbnails";
			return new List<DebugUI.Widget>
			{
				new DebugUI.Button
				{
					displayName = "Refresh",
					action = delegate
					{
						tc.Refresh();
					}
				}
			};
		}
		return null;
	}
```


## Nested types

- `Game.Debug.ThumbnailsDebugUI+<>c__DisplayClass0_0`  

