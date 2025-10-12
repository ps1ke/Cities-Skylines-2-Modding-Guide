# Game.AutoSaveSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Single m_LastAutoSaveCheck`  

## Properties

- `private System.Single timeSinceStartup { private get }`  

## Constructors

- `public AutoSaveSystem()`  

## Methods

- `private static AutoSave() : System.Threading.Tasks.Task`  
- `private CheckAutoSave(Game.Settings.GeneralSettings settings) : System.Void`  
- `private static GetAutoSaveDatabaseTarget() : Colossal.IO.AssetDatabase.ILocalAssetDatabase`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `private OnSettingsChanged(Game.Settings.Setting setting) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PerformAutoSave(Game.Settings.GeneralSettings settings) : System.Threading.Tasks.Task`  
- `private PruneAutoSaves(Game.Settings.GeneralSettings settings) : System.Void`  
- `private static SafeAutoSave() : System.Threading.Tasks.Task`  

## Nested types

- `Game.AutoSaveSystem+<>c`  
- `Game.AutoSaveSystem+<AutoSave>d__13`  
- `Game.AutoSaveSystem+<CheckAutoSave>d__9`  
- `Game.AutoSaveSystem+<PerformAutoSave>d__11`  

