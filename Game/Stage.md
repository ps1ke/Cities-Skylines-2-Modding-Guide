# Game.Stage

**Assembly:**  
**Namespace:** Game

**Type:** Enum

**Base:** System.Enum (underlying type: System.Int32)

**Summary:** The Stage enumeration represents the current high-level application stage of Cities: Skylines 2. It is used to distinguish between major runtime modes (no stage set, main menu UI, active gameplay, or editor mode). Mods and game systems can check this enum to gate logic that should only run in a particular mode (for example, only access in-game systems when Stage.Game is active, or only show editor-specific tools when Stage.Editor is active).
---

## Fields

- `None`  
Represents an unspecified or uninitialized stage (value 0). Useful as a default value before the game has established the current mode.

- `MainMenu`  
Indicates the game is currently at the main menu (value 1). UI-only systems and main-menu-specific logic should run here; many in-game subsystems are not available in this stage.

- `Game`  
Indicates active gameplay (value 2). Most runtime game systems and mod functionality that depends on the simulation should only run when the stage is Game.

- `Editor`  
Indicates the user is in an editor mode (value 3), such as map or scenario editing. Editor-specific tools and UI should be enabled here while some runtime systems may be disabled or behave differently.

## Properties

- This enum does not define properties.  
Enums in C# expose the typical System.Enum functionality but no custom properties are defined on this type.

## Constructors

- Enums cannot be instantiated directly with constructors in user code.  
The Stage enum values are the defined named constants (None, MainMenu, Game, Editor). Under the hood an enum has a default value corresponding to the underlying integral type (0 for None).

## Methods

- The Stage enum does not define instance methods.  
It inherits standard methods from System.Enum / System.ValueType / System.Object (for example ToString(), HasFlag(), GetHashCode(), etc.). Use these inherited methods as needed (e.g., stage.ToString()).

```csharp
namespace Game;

public enum Stage
{
	None,
	MainMenu,
	Game,
	Editor
}
```
