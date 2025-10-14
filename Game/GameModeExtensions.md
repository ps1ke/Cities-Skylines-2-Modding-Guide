# Game.GameModeExtensions

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** public static class GameModeExtensions

**Base:** System.Object

**Summary:** Provides extension helper methods for the GameMode enum used by Cities: Skylines 2. Includes a mapping to localization keys for rich-presence/status display and small bitmask checks for common mode queries (Editor, Game, GameOrEditor). These are lightweight, inlined-like helpers intended for readability and convenience when checking game mode flags or obtaining a localized status key.
---

## Fields

- None.  
This static class declares no instance or static fields.

## Properties

- None.  
No properties are defined.

## Constructors

- None.  
As a static class, it cannot be instantiated and defines no constructors.

## Methods

- `public static string ToRichPresence(this GameMode gameMode)`  
  Returns a localization key representing the current mode suitable for rich-presence/status display. Maps specific GameMode values to localization keys:
  - GameMode.MainMenu => "#StatusInMainMenu"
  - GameMode.Game => "#StatusInGame"
  - GameMode.Editor => "#StatusInEditor"
  For any other value, returns `string.Empty`. Note: the returned strings are localization keys (not user-facing text) and should be passed to the game's localization system before display.

- `public static bool IsEditor(this GameMode gameMode)`  
  Returns true when the GameMode has the Editor flag set. Implemented as a bitwise check: `(gameMode & GameMode.Editor) == GameMode.Editor`. Use to determine whether the current mode includes any editor capabilities.

- `public static bool IsGame(this GameMode gameMode)`  
  Returns true when the GameMode has the Game flag set. Implemented as `(gameMode & GameMode.Game) == GameMode.Game`. Use to check that the runtime is in a gameplay mode.

- `public static bool IsGameOrEditor(this GameMode gameMode)`  
  Returns true if the GameMode has either the Game or Editor flag (or both). Implemented as `(gameMode & GameMode.GameOrEditor) != 0`. Useful when behaviour should apply to both editing and gameplay contexts.

Usage examples:
- Obtaining the localization key:
  - `var key = currentMode.ToRichPresence();`
- Checking flags:
  - `if (currentMode.IsEditor()) { /* editor-only logic */ }`
  - `if (currentMode.IsGameOrEditor()) { /* logic common to game and editor */ }`

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

Notes and considerations:
- These methods operate on the GameMode enum and assume that GameMode is defined as a flags-capable enum (bitmask). Ensure the semantics of the enum match these checks.
- Because ToRichPresence returns localization keys, always resolve them through the game's localization system before presenting to users.
- The bitwise checks are cheap and suitable for frequent use (e.g., in update loops or UI state checks).