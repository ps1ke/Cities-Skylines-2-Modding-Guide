# Game.Settings.GraphicsSettingsExtensions

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class GraphicsSettingsExtensions
{
    public static UnityEngine.CursorLockMode ToUnityCursorMode(Game.Settings.GraphicsSettings+CursorMode mode);
}
```


## Methods

- `public static ToUnityCursorMode(Game.Settings.GraphicsSettings+CursorMode mode) : UnityEngine.CursorLockMode`  

```csharp
public static CursorLockMode ToUnityCursorMode(this GraphicsSettings.CursorMode mode)
	{
		return mode switch
		{
			GraphicsSettings.CursorMode.Free => CursorLockMode.None, 
			GraphicsSettings.CursorMode.ConfinedToWindow => CursorLockMode.Confined, 
			_ => throw new ArgumentException($"Unsupported cursor mode: {mode}", "mode"), 
		};
	}
```


