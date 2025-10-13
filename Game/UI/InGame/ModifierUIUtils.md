# Game.UI.InGame.ModifierUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ModifierUIUtils
{
    public static System.Single GetModifierDelta(Game.Prefabs.ModifierValueMode mode, System.Single delta);
    public static System.String GetModifierUnit(Game.Prefabs.ModifierValueMode mode);
}
```


## Methods

- `public static GetModifierDelta(Game.Prefabs.ModifierValueMode mode, System.Single delta) : System.Single`  

```csharp
public static float GetModifierDelta(ModifierValueMode mode, float delta)
	{
		return mode switch
		{
			ModifierValueMode.Relative => 100f * delta, 
			ModifierValueMode.InverseRelative => 100f * (1f / math.max(0.001f, 1f + delta) - 1f), 
			_ => delta, 
		};
	}
```

- `public static GetModifierUnit(Game.Prefabs.ModifierValueMode mode) : System.String`  

```csharp
public static string GetModifierUnit(ModifierValueMode mode)
	{
		if (mode == ModifierValueMode.Absolute)
		{
			return "floatSingleFraction";
		}
		return "percentage";
	}
```


