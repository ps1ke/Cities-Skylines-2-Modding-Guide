# Game.SystemUpdatePhase

**Assembly:** Assembly-CSharp  
**Namespace:** Game

**Type:** enum

**Base:** System.Int32

**Summary:** Enumeration of the engine/game update phases used by Cities: Skylines 2. These phases represent distinct points in the global update loop (simulation, rendering, tool handling, serialization, etc.) that systems or mods can target to run logic at a specific moment in the frame or lifecycle. Choose the phase that best matches when your code must run relative to simulation, rendering, tool processing, serialization, or cleanup.
---

## Fields

- `Invalid = -1`  
Represents an invalid or uninitialized phase.

- `MainLoop`  
Primary game loop entry phase. Early per-frame processing that is part of the core update.

- `LateUpdate`  
Executed after MainLoop; used for logic that must run after core per-frame updates but before modifications or simulation.

- `Modification1`  
First modification phase. Intended for making changes to game state before simulation; part of a series of modification phases.

- `Modification2`  
Second modification phase; further state modifications that should occur after Modification1.

- `Modification2B`  
An additional modification slot between Modification2 and Modification3 for ordering finer-grained changes.

- `Modification3`  
Third modification phase; continues ordered modifications to game state ahead of simulation.

- `Modification4`  
Fourth modification phase; used for later modifications before simulation.

- `Modification4B`  
Extra modification slot after Modification4 for finer ordering.

- `Modification5`  
Fifth modification phase; typically one of the last modification steps prior to modification end.

- `ModificationEnd`  
Marks the end of modification phases. Systems that must run after all modifications can target phases after this.

- `PreSimulation`  
Runs immediately before simulation step(s). Use this to prepare or finalize data that the simulation will consume.

- `PostSimulation`  
Runs immediately after simulation step(s). Good for processing results of simulation or scheduling follow-up tasks.

- `GameSimulation`  
Phase dedicated to game simulation logic (city simulation proper). Systems tied to simulation should run here.

- `EditorSimulation`  
Simulation phase specific to editor mode (if applicable). Used while editing rather than running the normal game simulation.

- `Rendering`  
Main rendering phase for drawing game visuals. Tasks that affect visuals or issue draw calls belong here.

- `PreTool`  
Phase before tool processing. Prepare tool state or visuals before tool update runs.

- `PostTool`  
Phase after tool processing. Cleanup or finalize actions related to tools go here.

- `ToolUpdate`  
Phase where tool logic (building tools, selection, placement, etc.) is updated.

- `ClearTool`  
Phase for clearing or resetting tool-related state.

- `ApplyTool`  
Phase for applying tool effects to game state (e.g., committing a placement).

- `Serialize`  
Phase for writing game state (serialization). Used when the engine performs save or state export operations.

- `Deserialize`  
Phase for reading game state (deserialization). Used when loading or restoring state.

- `UIUpdate`  
Phase for updating user interface elements each frame.

- `UITooltip`  
Phase for generating/updating UI tooltips. Runs near UI updates but focused on tooltip content.

- `PrefabUpdate`  
Phase for updating prefabs or prefab-related data (references, caches, etc.).

- `DebugGizmos`  
Phase reserved for debug drawing/gizmos. Used for debug overlays and developer visuals.

- `LoadSimulation`  
Phase related to loading or initializing simulation state (e.g., when a save is loaded).

- `PreCulling`  
Phase before culling operations. Prepare data or state that affects visibility determination.

- `CompleteRendering`  
Phase after primary rendering finishes; suitable for final render-stage operations/effects.

- `Raycast`  
Phase for performing raycasts used by tools, UI, or gameplay systems.

- `PrefabReferences`  
Phase for resolving or updating references between prefabs and other assets.

- `Cleanup`  
Final cleanup phase at the end of the frame or lifecycle; release temporary resources, finalize state.

## Properties

- None. This is a plain enum; it does not expose properties.

## Constructors

- N/A. Enums are value types and do not have user-defined constructors in typical usage.

## Methods

- None. This enum only defines named integer constants.

```csharp
namespace Game;

public enum SystemUpdatePhase
{
	Invalid = -1,
	MainLoop,
	LateUpdate,
	Modification1,
	Modification2,
	Modification2B,
	Modification3,
	Modification4,
	Modification4B,
	Modification5,
	ModificationEnd,
	PreSimulation,
	PostSimulation,
	GameSimulation,
	EditorSimulation,
	Rendering,
	PreTool,
	PostTool,
	ToolUpdate,
	ClearTool,
	ApplyTool,
	Serialize,
	Deserialize,
	UIUpdate,
	UITooltip,
	PrefabUpdate,
	DebugGizmos,
	LoadSimulation,
	PreCulling,
	CompleteRendering,
	Raycast,
	PrefabReferences,
	Cleanup
}
```

Notes for modders:
- Choose a phase that matches when your logic must run relative to simulation and rendering. Running heavy work inside rendering or simulation phases can affect performance or determinism.
- Some phases are specifically for tooling or editor contexts (EditorSimulation, ToolUpdate, etc.). Ensure your code checks runtime mode if it should run only in editor or play modes.