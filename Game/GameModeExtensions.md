# Game.GameModeExtensions

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class GameModeExtensions
{
    public static System.Boolean IsEditor(Game.GameMode gameMode);
    public static System.Boolean IsGame(Game.GameMode gameMode);
    public static System.Boolean IsGameOrEditor(Game.GameMode gameMode);
    public static System.String ToRichPresence(Game.GameMode gameMode);
}
```


## Methods

- `public static IsEditor(Game.GameMode gameMode) : System.Boolean`  

```csharp
public static bool IsEditor(this GameMode gameMode)
	{
		return (gameMode & GameMode.Editor) == GameMode.Editor;
	}
```

- `public static IsGame(Game.GameMode gameMode) : System.Boolean`  

```csharp
public static bool IsGame(this GameMode gameMode)
	{
		return (gameMode & GameMode.Game) == GameMode.Game;
	}
```

- `public static IsGameOrEditor(Game.GameMode gameMode) : System.Boolean`  

```csharp
public static bool IsGameOrEditor(this GameMode gameMode)
	{
		return (gameMode & GameMode.GameOrEditor) != 0;
	}
```

- `public static ToRichPresence(Game.GameMode gameMode) : System.String`  

```csharp
public static string ToRichPresence(this GameMode gameMode)
	{
		return gameMode switch
		{
			GameMode.MainMenu => "#StatusInMainMenu", 
			GameMode.Game => "#StatusInGame", 
			GameMode.Editor => "#StatusInEditor", 
			_ => string.Empty, 
		};
	}
```


