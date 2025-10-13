# Game.UI.ColorExtensions

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class ColorExtensions
{
    public static System.String ToHexCode(UnityEngine.Color color, System.Boolean ignoreAlpha);
}
```


## Methods

- `public static ToHexCode(UnityEngine.Color color, System.Boolean ignoreAlpha = False) : System.String`  

```csharp
public static string ToHexCode(this Color color, bool ignoreAlpha = false)
	{
		if (!ignoreAlpha)
		{
			return $"#{(int)(color.r * 255f):X2}{(int)(color.g * 255f):X2}{(int)(color.b * 255f):X2}{(int)(color.a * 255f):X2}";
		}
		return $"#{(int)(color.r * 255f):X2}{(int)(color.g * 255f):X2}{(int)(color.b * 255f):X2}";
	}
```


