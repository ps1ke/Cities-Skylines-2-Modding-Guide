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
[Preserve]
	public AutoSaveSystem()
	{
	}
```


## Methods

- `private static AutoSave() : System.Threading.Tasks.Task`  

```csharp
private static async Task AutoSave()
	{
		RenderTexture preview = ScreenCaptureHelper.CreateRenderTarget("PreviewSaveGame-Auto", 680, 383);
		ScreenCaptureHelper.CaptureScreenshot(Camera.main, preview, new MenuHelpers.SaveGamePreviewSettings());
		MenuUISystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<MenuUISystem>();
		string text = $"{DateTime.Now:dd-MMMM-HH-mm-ss}";
		COSystemBase.baseLog.InfoFormat("Auto-saving {0}...", text);
		try
		{
			ILocalAssetDatabase autoSaveDatabaseTarget = GetAutoSaveDatabaseTarget();
			if (autoSaveDatabaseTarget.Exists<PackageAsset>(SaveHelpers.GetAssetDataPath<SaveGameMetadata>(autoSaveDatabaseTarget, text), out var asset))
			{
				autoSaveDatabaseTarget.DeleteAsset(asset);
			}
			await GameManager.instance.Save(text, existingSystemManaged.GetSaveInfo(autoSave: true), autoSaveDatabaseTarget, preview);
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception);
		}
		finally
		{
			CoreUtils.Destroy(preview);
		}
	}
```

- `private CheckAutoSave(Game.Settings.GeneralSettings settings) : System.Void`  

```csharp
private async void CheckAutoSave(GeneralSettings settings)
	{
		if (timeSinceStartup - m_LastAutoSaveCheck > (float)settings.autoSaveInterval)
		{
			COSystemBase.baseLog.DebugFormat("Auto-save triggered after {0}s", m_LastAutoSaveCheck);
			m_LastAutoSaveCheck = timeSinceStartup;
			await PerformAutoSave(settings);
		}
	}
```

- `private static GetAutoSaveDatabaseTarget() : Colossal.IO.AssetDatabase.ILocalAssetDatabase`  

```csharp
private static ILocalAssetDatabase GetAutoSaveDatabaseTarget()
	{
		return AssetDatabase.user;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		SharedSettings.instance.general.onSettingsApplied += OnSettingsChanged;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		SharedSettings.instance.general.onSettingsApplied -= OnSettingsChanged;
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGameLoadingComplete(Purpose purpose, GameMode mode)
	{
		if ((purpose == Purpose.LoadGame || purpose == Purpose.NewGame) && SharedSettings.instance.general.autoSave)
		{
			COSystemBase.baseLog.Debug("Auto-save watch active!");
			m_LastAutoSaveCheck = timeSinceStartup;
		}
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		if (SharedSettings.instance.general.autoSave)
		{
			COSystemBase.baseLog.Debug("Auto-save watch inactive!");
			m_LastAutoSaveCheck = -1f;
		}
	}
```

- `private OnSettingsChanged(Game.Settings.Setting setting) : System.Void`  

```csharp
private void OnSettingsChanged(Setting setting)
	{
		if (!GameManager.instance.gameMode.IsGame() || !(setting is GeneralSettings generalSettings))
		{
			return;
		}
		if (generalSettings.autoSave)
		{
			if (m_LastAutoSaveCheck < 0f)
			{
				PruneAutoSaves(generalSettings);
				m_LastAutoSaveCheck = timeSinceStartup;
				COSystemBase.baseLog.Debug("Auto-save watch active!");
			}
		}
		else if (m_LastAutoSaveCheck >= 0f)
		{
			PruneAutoSaves(generalSettings);
			m_LastAutoSaveCheck = -1f;
			COSystemBase.baseLog.Debug("Auto-save watch inactive!");
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_LastAutoSaveCheck >= 0f && GameManager.instance.gameMode.IsGame())
		{
			GeneralSettings general = SharedSettings.instance.general;
			if (general.autoSave)
			{
				CheckAutoSave(general);
			}
		}
	}
```

- `public PerformAutoSave(Game.Settings.GeneralSettings settings) : System.Threading.Tasks.Task`  

```csharp
public async Task PerformAutoSave(GeneralSettings settings)
	{
		await SafeAutoSave();
		PruneAutoSaves(settings);
	}
```

- `private PruneAutoSaves(Game.Settings.GeneralSettings settings) : System.Void`  

```csharp
private void PruneAutoSaves(GeneralSettings settings)
	{
		if (settings.autoSaveCount == GeneralSettings.AutoSaveCount.Unlimited)
		{
			return;
		}
		try
		{
			List<SaveGameMetadata> source = (from s in GetAutoSaveDatabaseTarget().GetAssets(default(SearchFilter<SaveGameMetadata>))
				where s.target.autoSave
				orderby s.target.lastModified descending
				select s).ToList();
			int autoSaveCount = (int)settings.autoSaveCount;
			foreach (SaveGameMetadata item in source.Skip(autoSaveCount))
			{
				SaveHelpers.DeleteSaveGame(item);
			}
		}
		catch (Exception exception)
		{
			COSystemBase.baseLog.Error(exception, "An error occurred while pruning auto-saves");
		}
	}
```

- `private static SafeAutoSave() : System.Threading.Tasks.Task`  

```csharp
private static Task SafeAutoSave()
	{
		return TaskManager.instance.EnqueueTask("SaveLoadGame", AutoSave, 1);
	}
```


## Nested types

- `Game.AutoSaveSystem+<>c`  
- `Game.AutoSaveSystem+<AutoSave>d__13`  
- `Game.AutoSaveSystem+<CheckAutoSave>d__9`  
- `Game.AutoSaveSystem+<PerformAutoSave>d__11`  

