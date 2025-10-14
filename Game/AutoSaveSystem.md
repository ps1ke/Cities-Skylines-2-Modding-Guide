# Game.AutoSaveSystem

**Assembly:** Game  
**Namespace:** Game

**Type:** class

**Base:** GameSystemBase

**Summary:** Manages the game's automatic save workflow. Watches the user's auto-save setting, enables/disables the periodic auto-save "watch", triggers auto-saves when the configured interval elapses, prunes old auto-save files according to user limits, and performs the actual save operation (including creating a preview texture). Uses TaskManager to schedule the save task and logs errors if they occur.
---

## Fields

- `private float m_LastAutoSaveCheck = -1f`  
Tracks the last time (Time.realtimeSinceStartup) the auto-save check ran. A value of -1f indicates the auto-save watch is inactive.

## Properties

- `private float timeSinceStartup => UnityEngine.Time.realtimeSinceStartup`  
Convenience property that returns UnityEngine.Time.realtimeSinceStartup. Used to compute elapsed time for auto-save intervals.

## Constructors

- `public AutoSaveSystem()`  
Default constructor. Marked with [Preserve] in the source. Initializes the system (no custom logic in constructor; initialization happens in OnCreate).

## Methods

- `protected override void OnCreate()`  
Subscribes to SharedSettings.instance.general.onSettingsApplied so the system can react when general settings change (for example toggling auto-save). Calls base.OnCreate().

- `private void OnSettingsChanged(Setting setting)`  
Event handler invoked when general settings are applied. If the current mode is a game and the setting is GeneralSettings:
  - If autoSave is enabled and the watch is not already active, it prunes auto-saves, sets m_LastAutoSaveCheck to current time, and logs that the watch is active.
  - If autoSave is disabled and the watch is active, it prunes auto-saves, deactivates the watch (sets m_LastAutoSaveCheck = -1f), and logs the change.

- `protected override void OnDestroy()`  
Unsubscribes from SharedSettings.instance.general.onSettingsApplied and calls base.OnDestroy().

- `protected override void OnGamePreload(Purpose purpose, GameMode mode)`  
Called during preload. If auto-save is enabled in settings, ensures the auto-save watch starts as inactive (sets m_LastAutoSaveCheck = -1f and logs).

- `protected override void OnGameLoadingComplete(Purpose purpose, GameMode mode)`  
Called after a save/load or new game finishes loading. If loading purpose is LoadGame or NewGame and auto-save is enabled, activates the auto-save watch by setting m_LastAutoSaveCheck to the current time and logs activation.

- `protected override void OnUpdate()`  
Runs each frame. If auto-save watch is active (m_LastAutoSaveCheck >= 0) and current mode is a game, and autoSave setting is enabled, calls CheckAutoSave to determine if an auto-save should be performed.

- `private async void CheckAutoSave(GeneralSettings settings)`  
Checks whether the elapsed time since m_LastAutoSaveCheck exceeds settings.autoSaveInterval. If so:
  - Logs that auto-save was triggered,
  - Updates m_LastAutoSaveCheck to the current time,
  - Awaits PerformAutoSave(settings).

- `private void PruneAutoSaves(GeneralSettings settings)`  
Removes old auto-save files when the user has set a finite auto-save count:
  - If settings.autoSaveCount == Unlimited, returns immediately.
  - Otherwise queries the auto-save asset database for SaveGameMetadata assets with target.autoSave == true, orders by lastModified descending, then deletes saves that exceed the configured count using SaveHelpers.DeleteSaveGame.
  - Wraps logic in try/catch and logs exceptions.

- `public async Task PerformAutoSave(GeneralSettings settings)`  
Performs an auto-save by:
  - Awaiting SafeAutoSave() to schedule and run the save task,
  - Then calling PruneAutoSaves(settings) to remove older auto-saves.

- `private static Task SafeAutoSave()`  
Enqueues the actual AutoSave method as a named task on TaskManager: TaskManager.instance.EnqueueTask("SaveLoadGame", AutoSave, 1). Returns the task that runs AutoSave.

- `private static async Task AutoSave()`  
Performs the save operation on the scheduled task:
  - Creates a RenderTexture preview via ScreenCaptureHelper.CreateRenderTarget("PreviewSaveGame-Auto", 680, 383).
  - Captures a screenshot of Camera.main into the preview using MenuHelpers.SaveGamePreviewSettings.
  - Obtains the MenuUISystem to collect save metadata and constructs a timestamped save name using DateTime.Now with format "dd-MMMM-HH-mm-ss".
  - Logs the auto-save attempt.
  - Gets the auto-save asset database (GetAutoSaveDatabaseTarget()) and deletes any existing asset that would conflict with the new timestamped name.
  - Calls GameManager.instance.Save(name, saveInfo, autoSaveDatabaseTarget, preview) and awaits it.
  - Ensures the preview RenderTexture is destroyed in a finally block.
  - Catches and logs exceptions.

- `private static ILocalAssetDatabase GetAutoSaveDatabaseTarget()`  
Returns the ILocalAssetDatabase used for auto-saves. In this implementation it returns AssetDatabase.user (the user's local asset database).

```csharp
[Preserve]
    protected override void OnCreate()
    {
        base.OnCreate();
        SharedSettings.instance.general.onSettingsApplied += OnSettingsChanged;
    }
```