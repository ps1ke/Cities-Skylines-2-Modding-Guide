# Game.AutoSaveSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AutoSaveSystem : Game.GameSystemBase
{
    private System.Single m_LastAutoSaveCheck;

    private System.Single timeSinceStartup { private get; }

    public AutoSaveSystem();

    private static System.Threading.Tasks.Task AutoSave();
    private System.Void CheckAutoSave(Game.Settings.GeneralSettings settings);
    private static Colossal.IO.AssetDatabase.ILocalAssetDatabase GetAutoSaveDatabaseTarget();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    private System.Void OnSettingsChanged(Game.Settings.Setting setting);
    protected virtual System.Void OnUpdate();
    public System.Threading.Tasks.Task PerformAutoSave(Game.Settings.GeneralSettings settings);
    private System.Void PruneAutoSaves(Game.Settings.GeneralSettings settings);
    private static System.Threading.Tasks.Task SafeAutoSave();
}
```


## Fields

- `private System.Single m_LastAutoSaveCheck`  

```csharp
private System.Single m_LastAutoSaveCheck;
```


## Properties

- `private System.Single timeSinceStartup { private get }`  

```csharp
private System.Single timeSinceStartup { private get; }
```


## Constructors

- `public AutoSaveSystem()`  

```csharp
public AutoSaveSystem();
```


## Methods

- `private static AutoSave() : System.Threading.Tasks.Task`  

```csharp
private static System.Threading.Tasks.Task AutoSave();
```

- `private CheckAutoSave(Game.Settings.GeneralSettings settings) : System.Void`  

```csharp
private System.Void CheckAutoSave(Game.Settings.GeneralSettings settings);
```

- `private static GetAutoSaveDatabaseTarget() : Colossal.IO.AssetDatabase.ILocalAssetDatabase`  

```csharp
private static Colossal.IO.AssetDatabase.ILocalAssetDatabase GetAutoSaveDatabaseTarget();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `private OnSettingsChanged(Game.Settings.Setting setting) : System.Void`  

```csharp
private System.Void OnSettingsChanged(Game.Settings.Setting setting);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PerformAutoSave(Game.Settings.GeneralSettings settings) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task PerformAutoSave(Game.Settings.GeneralSettings settings);
```

- `private PruneAutoSaves(Game.Settings.GeneralSettings settings) : System.Void`  

```csharp
private System.Void PruneAutoSaves(Game.Settings.GeneralSettings settings);
```

- `private static SafeAutoSave() : System.Threading.Tasks.Task`  

```csharp
private static System.Threading.Tasks.Task SafeAutoSave();
```


## Nested types

- `Game.AutoSaveSystem+<>c`  
- `Game.AutoSaveSystem+<AutoSave>d__13`  
- `Game.AutoSaveSystem+<CheckAutoSave>d__9`  
- `Game.AutoSaveSystem+<PerformAutoSave>d__11`  

