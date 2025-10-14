# Game.GameMode

**Assembly:**  
**Namespace:** Game

**Type:** enum

**Base:** System.Enum

**Summary:** Defines a set of bit flags representing the different runtime modes the game can be in (e.g., Game, Editor, MainMenu). The enum is annotated with [Flags], so values can be combined with bitwise operations. Typical uses include checking the current mode or allowing functionality only in certain modes.
---

## Fields

- `None = 0`  
Represents no mode/flag set. Useful as a default or "unset" value.

- `Other = 1`  
A generic/other category for modes not explicitly listed by the enum. Treated as a single-bit flag.

- `Game = 2`  
Indicates the normal game play mode.

- `Editor = 4`  
Indicates an editor mode (e.g., map or asset editor).

- `MainMenu = 8`  
Indicates the main menu mode.

- `GameOrEditor = 6`  
A convenience combined flag equal to Game | Editor (2 | 4). Indicates either game or editor mode.

- `All = 0xF`  
All flags combined (Other | Game | Editor | MainMenu). Useful when you want to match any mode.

## Properties

- This enum exposes no properties. It is a simple flags enum used for bitwise checks.

## Constructors

- Enums do not define explicit constructors. Instances are represented by the named constant values above.

## Methods

- This enum defines no methods. Interaction is via standard enum/bitwise operations.

```csharp
// Original enum from the game:
using System;

namespace Game
{
    [Flags]
    public enum GameMode
    {
        None = 0,
        Other = 1,
        Game = 2,
        Editor = 4,
        MainMenu = 8,
        GameOrEditor = 6,
        All = 0xF
    }
}

// Typical usage example:
GameMode currentMode = GameMode.Game;

// Check if in Game mode:
bool isGame = (currentMode & GameMode.Game) == GameMode.Game;

// Check if in Game or Editor:
bool isGameOrEditor = (currentMode & GameMode.GameOrEditor) != 0;
```
