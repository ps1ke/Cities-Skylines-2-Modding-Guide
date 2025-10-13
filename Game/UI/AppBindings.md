# Game.UI.AppBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class AppBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding;
    private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation;
    private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding;
    private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites;
    private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites;
    private System.Action<System.Int32> m_ConfirmationDialogCallback;
    private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback;
    private Game.UI.Debug.DebugUISystem m_DebugUISystem;
    private System.Boolean <ready>k__BackingField;
    private System.String <activeUI>k__BackingField;
    private static Game.UI.AppBindings+FrameTiming m_FrameTiming;
    private static const System.String kGroup;
    public static const System.String kBodyClassNames;

    public System.Boolean ready { get; set; }
    public System.String activeUI { get; set; }

    public AppBindings();

    private System.Boolean <.ctor>b__30_0();
    private System.String <.ctor>b__30_1();
    public System.Void AddActiveUIModLocation(System.Collections.Generic.IList<System.String> locations);
    private System.Void DismissCurrentError();
    public System.Void Dispose();
    private System.Void ExitApplication();
    private System.Single GetCPUMainThreadTime();
    private System.Single GetCPURenderThreadTime();
    private System.Single GetFPS();
    private System.Single GetFullFrameTime();
    private System.Single GetGPUTime();
    private Game.Assets.SaveInfo GetLastSaveInfo();
    internal System.Threading.Tasks.Task<System.Boolean> LauncherContinueGame();
    private System.Void OnConfirmationDialogCallback(System.Int32 msg);
    private System.Void OnDismissibleConfirmationDialogCallback(System.Int32 msg, System.Boolean dontShowAgain);
    public System.Void RemoveActiveUIModLocation(System.Collections.Generic.IList<System.String> locations);
    private System.Void SaveBackup();
    private System.Void SaveBackupAndExitApplication();
    private System.Threading.Tasks.Task SaveBackupImpl();
    private System.Void SetClipboard(System.String text);
    public System.Void SetEditorActive();
    public System.Void SetGameActive();
    public System.Void SetMainMenuActive();
    public System.Void SetNoneActive();
    public System.Void ShowConfirmationDialog(Game.UI.ConfirmationDialog dialog, System.Action<System.Int32> callback);
    public System.Void ShowConfirmationDialog(Game.UI.DismissibleConfirmationDialog dialog, System.Action<System.Int32, System.Boolean> callback);
    public System.Void ShowMessageDialog(Game.UI.MessageDialog dialog, System.Action<System.Int32> callback);
    public virtual System.Boolean Update();
    public System.Void UpdateActiveUIModsLocation(System.Collections.Generic.IList<System.String> locations);
    public System.Void UpdateCanContinueBinding();
    public System.Void UpdateOwnedPrerequisiteBinding();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_BackgroundProcessMessageBinding;
```

- `private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding`  

```csharp
private Colossal.UI.Binding.EventBinding<Game.UI.ConfirmationDialogBase> m_ConfirmationDialogBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.HashSet<System.String>> m_ActiveUIModsLocation;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Assets.SaveInfo> m_CanContinueBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String[]> m_OwnedPrerequisites;
```

- `private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites`  

```csharp
private Colossal.UI.Binding.EventBinding m_CheckContinueGamePrerequisites;
```

- `private System.Action<System.Int32> m_ConfirmationDialogCallback`  

```csharp
private System.Action<System.Int32> m_ConfirmationDialogCallback;
```

- `private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback`  

```csharp
private System.Action<System.Int32, System.Boolean> m_DismissibleConfirmationDialogCallback;
```

- `private Game.UI.Debug.DebugUISystem m_DebugUISystem`  

```csharp
private Game.UI.Debug.DebugUISystem m_DebugUISystem;
```

- `private System.Boolean <ready>k__BackingField`  

```csharp
private System.Boolean <ready>k__BackingField;
```

- `private System.String <activeUI>k__BackingField`  

```csharp
private System.String <activeUI>k__BackingField;
```

- `private static Game.UI.AppBindings+FrameTiming m_FrameTiming`  

```csharp
private static Game.UI.AppBindings+FrameTiming m_FrameTiming;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `public static const System.String kBodyClassNames`  

```csharp
public static const System.String kBodyClassNames;
```


## Properties

- `public System.Boolean ready { get; set }`  

```csharp
public System.Boolean ready { get; set; }
```

- `public System.String activeUI { get; set }`  

```csharp
public System.String activeUI { get; set; }
```


## Constructors

- `public AppBindings()`  

```csharp
public AppBindings()
	{
		ErrorDialogManager.Initialize();
		AddUpdateBinding(new GetterValueBinding<bool>("app", "ready", () => ready));
		AddUpdateBinding(new GetterValueBinding<string>("app", "activeUI", () => activeUI, ValueWriters.Nullable(new StringWriter())));
		AddBinding(new ValueBinding<string>("app", "bodyClassNames", ""));
		AddUpdateBinding(new GetterValueBinding<int>("app", "fpsMode", () => (int)(SharedSettings.instance?.general.fpsMode ?? GeneralSettings.FPSMode.Off)));
		AddUpdateBinding(new GetterValueBinding<FrameTiming>("app", "frameStats", () => m_FrameTiming, new ValueWriter<FrameTiming>()));
		AddUpdateBinding(new GetterValueBinding<string>("app", "activeLocale", () => GameManager.instance.localizationManager.activeDictionary.localeID));
		AddUpdateBinding(new GetterValueBinding<ErrorDialog>("app", "currentError", () => ErrorDialogManager.currentErrorDialog, ValueWriters.Nullable(new ValueWriter<ErrorDialog>())));
		AddBinding(m_BackgroundProcessMessageBinding = new ValueBinding<string>("app", "backgroundProcessMessage", null, ValueWriters.Nullable(new StringWriter())));
		AddBinding(new TriggerBinding<string>("app", "setClipboard", SetClipboard));
		AddBinding(new TriggerBinding("app", "exitApplication", ExitApplication));
		AddBinding(new TriggerBinding("app", "saveBackupAndExitApplication", SaveBackupAndExitApplication));
		AddBinding(new TriggerBinding("app", "saveBackup", SaveBackup));
		AddBinding(new TriggerBinding("app", "dismissCurrentError", DismissCurrentError));
		AddBinding(m_ConfirmationDialogBinding = new EventBinding<ConfirmationDialogBase>("app", "confirmationDialog", new ValueWriter<ConfirmationDialogBase>()));
		AddBinding(new TriggerBinding<int>("app", "confirmationDialogCallback", OnConfirmationDialogCallback));
		AddBinding(new TriggerBinding<int, bool>("app", "dismissibleConfirmationDialogCallback", OnDismissibleConfirmationDialogCallback));
		AddBinding(m_ActiveUIModsLocation = new ValueBinding<HashSet<string>>("app", "activeUIModsLocation", new HashSet<string>(), new CollectionWriter<string>()));
		AddBinding(new GetterValueBinding<int>("app", "platform", () => (int)Application.platform.ToPlatform()));
		AddBinding(m_CanContinueBinding = new GetterValueBinding<SaveInfo>("app", "canContinueGame", GetLastSaveInfo, ValueWriters.Nullable(new ValueWriter<SaveInfo>())));
		AddBinding(m_OwnedPrerequisites = new ValueBinding<string[]>("app", "ownedPrerequisites", null, new NullableWriter<string[]>(new ArrayWriter<string>())));
		AddBinding(new CallBinding<string[], bool>("app", "arePrerequisitesMet", GameManager.instance.ArePrerequisitesMet, new NullableReader<string[]>(new ArrayReader<string>())));
		AddBinding(m_CheckContinueGamePrerequisites = new EventBinding("app", "checkContinueGamePrerequisites"));
	}
```


## Methods

- `private <.ctor>b__30_0() : System.Boolean`  

```csharp
private System.Boolean <.ctor>b__30_0();
```

- `private <.ctor>b__30_1() : System.String`  

```csharp
private System.String <.ctor>b__30_1();
```

- `public AddActiveUIModLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  

```csharp
public void AddActiveUIModLocation(IList<string> locations)
	{
		int count = m_ActiveUIModsLocation.value.Count;
		foreach (string location in locations)
		{
			m_ActiveUIModsLocation.value.Add(location);
		}
		if (m_ActiveUIModsLocation.value.Count != count)
		{
			m_ActiveUIModsLocation.TriggerUpdate();
		}
	}
```

- `private DismissCurrentError() : System.Void`  

```csharp
private void DismissCurrentError()
	{
		ErrorDialogManager.DismissCurrentErrorDialog();
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		ErrorDialogManager.Dispose();
		m_FrameTiming.Dispose();
	}
```

- `private ExitApplication() : System.Void`  

```csharp
private void ExitApplication()
	{
		GameManager.QuitGame();
	}
```

- `private GetCPUMainThreadTime() : System.Single`  

```csharp
private float GetCPUMainThreadTime()
	{
		return (HDRenderPipeline.currentPipeline?.debugDisplaySettings?.debugFrameTiming?.m_FrameHistory?.SampleAverage.MainThreadCPUFrameTime).GetValueOrDefault();
	}
```

- `private GetCPURenderThreadTime() : System.Single`  

```csharp
private float GetCPURenderThreadTime()
	{
		return (HDRenderPipeline.currentPipeline?.debugDisplaySettings?.debugFrameTiming?.m_FrameHistory?.SampleAverage.RenderThreadCPUFrameTime).GetValueOrDefault();
	}
```

- `private GetFPS() : System.Single`  

```csharp
private float GetFPS()
	{
		GeneralSettings generalSettings = SharedSettings.instance?.general;
		if (generalSettings != null && generalSettings.fpsMode == GeneralSettings.FPSMode.Precise)
		{
			return HDRenderPipeline.currentPipeline?.debugDisplaySettings?.debugFrameTiming?.m_FrameHistory?.SampleAverage.FramesPerSecond ?? (1f / Time.smoothDeltaTime);
		}
		return 1f / Time.smoothDeltaTime;
	}
```

- `private GetFullFrameTime() : System.Single`  

```csharp
private float GetFullFrameTime()
	{
		return (HDRenderPipeline.currentPipeline?.debugDisplaySettings?.debugFrameTiming?.m_FrameHistory?.SampleAverage.FullFrameTime).GetValueOrDefault();
	}
```

- `private GetGPUTime() : System.Single`  

```csharp
private float GetGPUTime()
	{
		return (HDRenderPipeline.currentPipeline?.debugDisplaySettings?.debugFrameTiming?.m_FrameHistory?.SampleAverage.GPUFrameTime).GetValueOrDefault();
	}
```

- `private GetLastSaveInfo() : Game.Assets.SaveInfo`  

```csharp
private SaveInfo GetLastSaveInfo()
	{
		SaveGameMetadata lastSaveGameMetadata = GameManager.instance.settings.userState.lastSaveGameMetadata;
		if (lastSaveGameMetadata != null && lastSaveGameMetadata.isValidSaveGame)
		{
			return lastSaveGameMetadata.target;
		}
		return null;
	}
```

- `internal LauncherContinueGame() : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
internal Task<bool> LauncherContinueGame()
	{
		m_CheckContinueGamePrerequisites.Trigger();
		return Task.FromResult(result: true);
	}
```

- `private OnConfirmationDialogCallback(System.Int32 msg) : System.Void`  

```csharp
private void OnConfirmationDialogCallback(int msg)
	{
		if (m_ConfirmationDialogCallback != null)
		{
			Action<int> confirmationDialogCallback = m_ConfirmationDialogCallback;
			m_ConfirmationDialogCallback = null;
			confirmationDialogCallback(msg);
		}
	}
```

- `private OnDismissibleConfirmationDialogCallback(System.Int32 msg, System.Boolean dontShowAgain) : System.Void`  

```csharp
private void OnDismissibleConfirmationDialogCallback(int msg, bool dontShowAgain)
	{
		if (m_DismissibleConfirmationDialogCallback != null)
		{
			Action<int, bool> dismissibleConfirmationDialogCallback = m_DismissibleConfirmationDialogCallback;
			m_DismissibleConfirmationDialogCallback = null;
			dismissibleConfirmationDialogCallback(msg, dontShowAgain);
		}
	}
```

- `public RemoveActiveUIModLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  

```csharp
public void RemoveActiveUIModLocation(IList<string> locations)
	{
		int count = m_ActiveUIModsLocation.value.Count;
		foreach (string location in locations)
		{
			m_ActiveUIModsLocation.value.Remove(location);
		}
		if (m_ActiveUIModsLocation.value.Count != count)
		{
			m_ActiveUIModsLocation.TriggerUpdate();
		}
	}
```

- `private SaveBackup() : System.Void`  

```csharp
private async void SaveBackup()
	{
		await SaveBackupImpl();
	}
```

- `private SaveBackupAndExitApplication() : System.Void`  

```csharp
private async void SaveBackupAndExitApplication()
	{
		await SaveBackupImpl();
		GameManager.QuitGame();
	}
```

- `private SaveBackupImpl() : System.Threading.Tasks.Task`  

```csharp
private async Task SaveBackupImpl()
	{
		RenderTexture preview = ScreenCaptureHelper.CreateRenderTarget("PreviewSaveGame-Exit", 680, 383);
		ScreenCaptureHelper.CaptureScreenshot(Camera.main, preview, new MenuHelpers.SaveGamePreviewSettings());
		ScreenCaptureHelper.AsyncRequest request = new ScreenCaptureHelper.AsyncRequest(preview);
		MenuUISystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<MenuUISystem>();
		string saveName = "SaveRecovery" + DateTime.Now.ToString("dd-MMMM-HH-mm-ss");
		try
		{
			await GameManager.instance.Save(saveName, existingSystemManaged.GetSaveInfo(autoSave: false), AssetDatabase.user, request);
		}
		catch (Exception exception)
		{
			CompositeBinding.log.Error(exception);
		}
		finally
		{
			await request.Dispose();
			CoreUtils.Destroy(preview);
		}
	}
```

- `private SetClipboard(System.String text) : System.Void`  

```csharp
private void SetClipboard(string text)
	{
		GUIUtility.systemCopyBuffer = text;
	}
```

- `public SetEditorActive() : System.Void`  

```csharp
public void SetEditorActive()
	{
		activeUI = "Editor";
	}
```

- `public SetGameActive() : System.Void`  

```csharp
public void SetGameActive()
	{
		activeUI = "Game";
	}
```

- `public SetMainMenuActive() : System.Void`  

```csharp
public void SetMainMenuActive()
	{
		activeUI = "Menu";
	}
```

- `public SetNoneActive() : System.Void`  

```csharp
public void SetNoneActive()
	{
		activeUI = null;
	}
```

- `public ShowConfirmationDialog(Game.UI.ConfirmationDialog dialog, System.Action<System.Int32> callback) : System.Void`  

```csharp
public void ShowConfirmationDialog([NotNull] DismissibleConfirmationDialog dialog, [NotNull] Action<int, bool> callback)
	{
		m_DismissibleConfirmationDialogCallback = callback;
		m_ConfirmationDialogBinding.Trigger(dialog);
	}
```

- `public ShowConfirmationDialog(Game.UI.DismissibleConfirmationDialog dialog, System.Action<System.Int32, System.Boolean> callback) : System.Void`  

```csharp
public void ShowConfirmationDialog([NotNull] DismissibleConfirmationDialog dialog, [NotNull] Action<int, bool> callback)
	{
		m_DismissibleConfirmationDialogCallback = callback;
		m_ConfirmationDialogBinding.Trigger(dialog);
	}
```

- `public ShowMessageDialog(Game.UI.MessageDialog dialog, System.Action<System.Int32> callback) : System.Void`  

```csharp
public void ShowMessageDialog([NotNull] MessageDialog dialog, Action<int> callback)
	{
		m_ConfirmationDialogCallback = callback;
		m_ConfirmationDialogBinding.Trigger(dialog);
	}
```

- `public virtual Update() : System.Boolean`  

```csharp
public override bool Update()
	{
		m_FrameTiming.Update();
		AdaptiveDynamicResolutionScale instance = AdaptiveDynamicResolutionScale.instance;
		DebugManager.instance.adaptiveDRSActive = instance.isEnabled && instance.isAdaptive;
		DebugFrameTiming debugFrameTiming = HDRenderPipeline.currentPipeline?.debugDisplaySettings?.debugFrameTiming;
		if (debugFrameTiming != null)
		{
			FrameTimeSample sample = debugFrameTiming.m_Sample;
			instance.UpdateDRS(sample.FullFrameTime, sample.MainThreadCPUFrameTime, sample.RenderThreadCPUFrameTime, sample.GPUFrameTime);
		}
		return base.Update();
	}
```

- `public UpdateActiveUIModsLocation(System.Collections.Generic.IList<System.String> locations) : System.Void`  

```csharp
public void UpdateActiveUIModsLocation(IList<string> locations)
	{
		HashSet<string> newValue = new HashSet<string>(locations);
		m_ActiveUIModsLocation.Update(newValue);
	}
```

- `public UpdateCanContinueBinding() : System.Void`  

```csharp
public void UpdateCanContinueBinding()
	{
		m_CanContinueBinding.Update();
	}
```

- `public UpdateOwnedPrerequisiteBinding() : System.Void`  

```csharp
public void UpdateOwnedPrerequisiteBinding()
	{
		string[] availablePrerequisitesNames = GameManager.instance.GetAvailablePrerequisitesNames();
		m_OwnedPrerequisites.Update(availablePrerequisitesNames);
	}
```


## Nested types

- `Game.UI.AppBindings+FrameTiming`  
- `Game.UI.AppBindings+<>c`  
- `Game.UI.AppBindings+<SaveBackup>d__42`  
- `Game.UI.AppBindings+<SaveBackupAndExitApplication>d__41`  
- `Game.UI.AppBindings+<SaveBackupImpl>d__43`  

