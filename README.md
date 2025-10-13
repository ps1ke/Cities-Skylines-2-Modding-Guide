# Cities: Skylines 2 Modding Documentation

I am starting here to create a documentation page for modding Cities Skylines II. The end goal will be to have a better suited website for this and then also use AI to create more detailed analysis of code snippets.

For now, this is what you need to know to get started.

Modding in Cities Skylines II mainly comes from using classes declared and developed specific for the Game, altough you can use other libraries like System or Unity (or at least I think, for now...). 
In the following documentation pages, only `Colossal.dll`, `Game.dll` and `PDX.SDK.dll` will be covered. 
To know the other libraries that you can use, navigate to `\Cities Skylines II\Cities2_Data\Managed` and there is listed all of the Dinamic Libraries you can use, like `System.dll` or `Unity.Burst`.

-   [Colossal.dll](#Colossal/index.md)
-   [Game.dll](#Game/index.md)
-   [PDX.SDK.dll](#PDX/index.md)

## Beginner’s guide 

This is an **absolute beginner’s guide** to start modding *Cities: Skylines II*.  
By the end of this tutorial, you’ll be able to make the game launch a terminal so you can start debugging your mod.

Currently, this guide is meant for those who want to use the most **default setup** possible, without changing much configuration.  
A minimal setup (without Visual Studio) will be covered in a future section of this guide.

---

## Table of Contents

-   [Getting Started](#getting-started)
    
-   [Installing Visual Studio](#installing-visual-studio)
    
-   [Non-Default Game Installation Path](#non-default-game-installation-path)
    
-   [Writing Your First Lines of Code](#writing-your-first-lines-of-code)
    
-   [Attaching the Unity Debugger](#attaching-the-unity-debugger)
  
-   [Launching the game with Developer Mode](#launching-the-game-with-developer-mode)
    
-   [Setting Up a UI Mod](#setting-up-a-ui-mod)
    
-   [Minimal Configuration (Coming Soon)](#minimal-or-bare-needed-configuration-and-requirements)
    

---

## Getting Started

To get started, open the game and go to:  
**Options → Modding → Automatic Install**

This will install:

-   **Unity**
    
-   **.NET SDKs**
    
-   **Node.js**
    

These will be installed on your default system drive.

> 💡 *If you prefer installing them elsewhere, you can do it manually—it’s not hard.*

---

### Unity License Setup

After Unity installs, the game might not automatically set up the required license.  
To fix this:

1.  Install **Unity Hub**: [https://unity.com/unity-hub](https://unity.com/unity-hub)
    
2.  Log in with a free Unity account.
    
3.  Once your account and license are active, Unity should be recognized by the game.
    

![Unity setup screenshot](https://github.com/user-attachments/assets/13b6a44d-b81d-40d0-a8f9-a84157443e64)

For any missing or outdated details, check the official wiki:  
🔗 [https://cs2.paradoxwikis.com/Modding\_Toolchain](https://cs2.paradoxwikis.com/Modding_Toolchain)

---

## Installing Visual Studio

Download Visual Studio:  
👉 [https://visualstudio.microsoft.com/](https://visualstudio.microsoft.com/)

When installing, select these **workloads**:

-   ✅ **.NET Desktop Development** (mandatory)
    
-   ✅ **Game Development with Unity** (needed for debugging)

<img width="589" height="604" alt="{F11E90D4-75F7-4125-A638-2ADEB193099C}" src="https://github.com/user-attachments/assets/f70d400b-cf4d-4e3d-906d-3541d266e54c" />

> ⚠️ The *Cities: Skylines II Mod Project Template* only appears **after** installing `.NET Desktop Development`.

![Visual Studio workload screenshot](https://github.com/user-attachments/assets/5717148c-3f6f-4868-a2e4-db96ef706dbc)

---

## Non-Default Game Installation Path

If your game is **not** installed in the default directory, you’ll need to update the path in Visual Studio.

**Steps:**

1.  In Visual Studio:  
    `Solution Explorer → [Your Mod Name] → Properties → Mod.props`
    
2.  Open the `Mod.props` file and update the paths as needed:
    

```xml
<SteamDefaultManagedPath>
  C:\Program Files (x86)\Steam\steamapps\common\Cities Skylines II\Cities2_Data\Managed
</SteamDefaultManagedPath>

<XboxDefaultManagedPath>
  F:\xbox\Cities - Skylines II - PC Edition\Content\Cities2_Data\Managed
</XboxDefaultManagedPath>
```

Save your changes and build your mod.  
The default template will include an example **Options Menu** in-game.

---

### Mod Entry Files

Two files act as the main entry points for your mod:

-   **`Mod.cs`** – main code entry point
    
-   **`Settings.cs`** – in-game options menu logic
    

If you build successfully, your mod will load next time you launch the game.

> ⚠️ You might get a harmless Visual Studio error saying it failed to build a “Class Library” — you can safely ignore it if the `.dll` was created.

---

### Debugging Build Errors

If you encounter errors related to missing .NET SDKs or dependencies, navigate to:

```css
Cities - Skylines II - PC Edition\Content\Cities2_Data\Content\Game\.ModdingToolchain\ModPostProcessor
```

Open a terminal there and run:

```bash
.\ModPostProcessor.exe
```

This tool can give extra details about missing dependencies or other build issues.

---

## Writing Your First Lines of Code

As with most programming tutorials, let’s start by printing **“Hello World!”** in your mod.

In your `Mod.cs` file, add a `ConsoleWindow` to the class:

```csharp
using Game.Debug;
using System;

namespace mod
{
    public class Mod : IMod
    {

        private ConsoleWindow console;

        public static ILog log = LogManager.GetLogger($"{nameof(mod2)}.{nameof(Mod)}").SetShowsErrorsInUI(false);
        private Setting m_Setting;
        public static ProxyAction m_ButtonAction;
        public static ProxyAction m_AxisAction;
        public static ProxyAction m_VectorAction;
        ...
```

Next, initialize the console in the `OnLoad(UpdateSystem updateSystem)` method:

```csharp
console = new ConsoleWindow("Cities: Skylines II Debug Console", attachConsole: true);
Console.WriteLine("Hello World!");
```

---

### Exploring Game APIs

There’s currently **no official documentation** for all modding classes and methods.  
Until then, you can inspect them through Visual Studio’s **Object Browser**:

```arduino
Solution Explorer → Dependencies → Assemblies → [Double-click any assembly]
```

You’ll see the disassembled structures, fields, and methods of each class.

More info:

-   [Community-made guides](https://cs2.paradoxwikis.com/Community-made_guides)
    
-   [Official Modding Category](https://cs2.paradoxwikis.com/Category:Modding)
    

---

## Attaching the Unity Debugger

Attaching the Unity Debugger allows you to set **breakpoints**, **inspect variables**, and **pause the game runtime**.

Follow this official guide:  
🔗 [https://cs2.paradoxwikis.com/Debugging](https://cs2.paradoxwikis.com/Debugging)

### Note

In some installations, the `boot.config` file isn’t in `Content\` but rather in:

```css
Cities - Skylines II - PC Edition\Content\Cities2_Data
```

Search for it if necessary.

If done correctly, the game will show a small **“Development Build”** label in the bottom-right corner of the main menu.

Then in Visual Studio:

> `Debug → Attach Unity Debugger`

Select the *Cities: Skylines II* process. You can now add breakpoints and inspect your mod live.

---

## Launching the game with Developer Mode

To start the game with Developer Mode, the following [wiki page](https://cs2.paradoxwikis.com/Developer_mode) should be enough.

In my case (using XBox Game pass), instead of creating a shortcut of the game executable I had to make from the launcher, and that was not the same listed in the wiki page but instead `gamelaunchhelper.exe` inside `Cities- Skylines II - PC Edition\Content` folder.
Also, not yet managed to use `-uiDeveloperMode`.

<img width="150" height="529" alt="image" src="https://github.com/user-attachments/assets/3d4088e4-1871-4a97-9cc5-c2285693627c" />


---

## Setting Up a UI Mod

🚧 *Coming soon.*

---

## Minimal or Bare Configuration and Requirements

🚧 *Also coming soon.*
