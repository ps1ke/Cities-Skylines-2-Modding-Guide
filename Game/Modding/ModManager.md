# Game.Modding.ModManager

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Game.Modding.ModManager+ModInfo>`, `System.Collections.IEnumerable`, `System.IDisposable`  

## Code

```csharp
public class ModManager : System.Collections.Generic.IEnumerable<Game.Modding.ModManager+ModInfo>, System.Collections.IEnumerable, System.IDisposable
{
    private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos;
    private System.Boolean m_Disabled;
    private System.Boolean m_Initialized;
    private System.Boolean m_IsInProgress;
    private System.Boolean <restartRequired>k__BackingField;
    private static Colossal.Logging.ILog log;
    private static const System.String kBurstSuffix;

    public System.Boolean isInitialized { get; }
    public System.Boolean restartRequired { get; private set; }

    private ModManager();
    public ModManager(System.Boolean disabled);

    private System.Void <RequireRestart>b__27_0();
    private System.Void <RequireRestart>b__27_1(System.Int32 msg);
    public System.Void AddUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule);
    public static System.Boolean AreModsEnabled();
    public System.Void Dispose();
    public System.Collections.Generic.IEnumerator<Game.Modding.ModManager+ModInfo> GetEnumerator();
    public static System.String[] GetModsEnabled();
    public System.Void Initialize(Game.UpdateSystem updateSystem);
    private System.Void InitializeMods(Game.UpdateSystem updateSystem);
    private System.Void InitializeUIModules();
    public System.String[] ListModsEnabled();
    private System.Void RegisterMods();
    public System.Void RemoveUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule);
    public System.Void RequireRestart();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Boolean TryGetExecutableAsset(Game.Modding.IMod mod, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
    public System.Boolean TryGetExecutableAsset(System.Reflection.Assembly assembly, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos`  

```csharp
private readonly System.Collections.Generic.List<Game.Modding.ModManager+ModInfo> m_ModsInfos;
```

- `private System.Boolean m_Disabled`  

```csharp
private System.Boolean m_Disabled;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.Boolean m_IsInProgress`  

```csharp
private System.Boolean m_IsInProgress;
```

- `private System.Boolean <restartRequired>k__BackingField`  

```csharp
private System.Boolean <restartRequired>k__BackingField;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static const System.String kBurstSuffix`  

```csharp
private static const System.String kBurstSuffix;
```


## Properties

- `public System.Boolean isInitialized { get }`  

```csharp
public System.Boolean isInitialized { get; }
```

- `public System.Boolean restartRequired { get; private set }`  

```csharp
public System.Boolean restartRequired { get; private set; }
```


## Constructors

- `private ModManager()`  

```csharp
public ModManager(bool disabled)
	{
		m_Disabled = disabled;
		if (!disabled)
		{
			ProgressState? progressState = ProgressState.Indeterminate;
			NotificationSystem.Push("ModLoadingStatus", null, null, "ModsLoading", "ModsLoadingWaiting", null, progressState);
		}
	}
```

- `public ModManager(System.Boolean disabled)`  

```csharp
public ModManager(bool disabled)
	{
		m_Disabled = disabled;
		if (!disabled)
		{
			ProgressState? progressState = ProgressState.Indeterminate;
			NotificationSystem.Push("ModLoadingStatus", null, null, "ModsLoading", "ModsLoadingWaiting", null, progressState);
		}
	}
```


## Methods

- `private <RequireRestart>b__27_0() : System.Void`  

```csharp
private System.Void <RequireRestart>b__27_0();
```

- `private <RequireRestart>b__27_1(System.Int32 msg) : System.Void`  

```csharp
private System.Void <RequireRestart>b__27_1(System.Int32 msg);
```

- `public AddUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule) : System.Void`  

```csharp
public void AddUIModule(UIModuleAsset uiModule)
	{
		if (m_Initialized)
		{
			UIManager.defaultUISystem.AddHostLocation("ui-mods", Path.GetDirectoryName(uiModule.path), uiModule.isLocal);
			GameManager.instance.userInterface.appBindings.AddActiveUIModLocation(new string[1] { uiModule.couiPath });
			log.InfoFormat("Registered UI Module {0} from {1}", uiModule.moduleInfo, uiModule);
		}
	}
```

- `public static AreModsEnabled() : System.Boolean`  

```csharp
public static bool AreModsEnabled()
	{
		GameManager instance = GameManager.instance;
		if ((object)instance == null)
		{
			return false;
		}
		return instance.modManager?.ListModsEnabled().Length > 0;
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.InfoFormat($"Mods disposed in {0}ms", t.TotalMilliseconds);
		}))
		{
			foreach (ModInfo modInfo in m_ModsInfos)
			{
				try
				{
					using (PerformanceCounter.Start(delegate(TimeSpan t)
					{
						log.InfoFormat($"Disposed {{1}} in {0}ms", t.TotalMilliseconds, modInfo.name);
					}))
					{
						modInfo.Dispose();
					}
				}
				catch (Exception exception)
				{
					log.ErrorFormat(exception, "Error disposing mod {0} ({1})", modInfo.name, modInfo.assemblyFullName);
				}
			}
			m_ModsInfos.Clear();
		}
	}
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.Modding.ModManager+ModInfo>`  

```csharp
public IEnumerator<ModInfo> GetEnumerator()
	{
		return m_ModsInfos.GetEnumerator();
	}
```

- `public static GetModsEnabled() : System.String[]`  

```csharp
public static string[] GetModsEnabled()
	{
		return GameManager.instance?.modManager?.ListModsEnabled();
	}
```

- `public Initialize(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
public void Initialize(UpdateSystem updateSystem)
	{
		if (m_Disabled || m_Initialized || m_IsInProgress)
		{
			return;
		}
		try
		{
			m_IsInProgress = true;
			LocalizedString? text = "Initializing mods";
			ProgressState? progressState = ProgressState.Indeterminate;
			NotificationSystem.Push("ModLoadingStatus", null, text, "ModsLoading", null, null, progressState);
			RegisterMods();
			InitializeMods(updateSystem);
			m_Initialized = true;
			int num = 0;
			foreach (ModInfo modsInfo in m_ModsInfos)
			{
				ModInfo modInfo = modsInfo;
				if (modInfo.state < ModInfo.State.IsNotModWarning)
				{
					continue;
				}
				num++;
				string id = modInfo.asset.GetHashCode().ToString();
				string text2 = (string.IsNullOrEmpty(modInfo.asset.mod.thumbnailPath) ? null : $"{modInfo.asset.mod.thumbnailPath}?width={NotificationUISystem.width})");
				ProgressState progressState2 = modInfo.state switch
				{
					ModInfo.State.IsNotModWarning => ProgressState.Warning, 
					ModInfo.State.IsNotUniqueWarning => ProgressState.Warning, 
					ModInfo.State.GeneralError => ProgressState.Failed, 
					ModInfo.State.MissedDependenciesError => ProgressState.Failed, 
					ModInfo.State.LoadAssemblyError => ProgressState.Failed, 
					ModInfo.State.LoadAssemblyReferenceError => ProgressState.Failed, 
					_ => ProgressState.Failed, 
				};
				string identifier = id;
				LocalizedString? title = modInfo.asset.mod.displayName;
				string thumbnail = text2;
				progressState = progressState2;
				NotificationSystem.Push(identifier, title, null, null, "ModsLoadingFailed", thumbnail, progressState, null, delegate
				{
					string text3 = "Common.DIALOG_TITLE_MODDING[" + ((progressState2 == ProgressState.Warning) ? "ModLoadingWarning" : "ModLoadingError") + "]";
					LocalizedString message = new LocalizedString($"Common.DIALOG_MESSAGE_MODDING[{modInfo.state}]", null, new Dictionary<string, ILocElement> { 
					{
						"MODNAME",
						LocalizedString.Value(modInfo.asset.mod.displayName)
					} });
					LocalizedString[] otherActions = (modInfo.asset.isLocal ? Array.Empty<LocalizedString>() : new LocalizedString[2]
					{
						LocalizedString.Id("Common.DIALOG_MESSAGE_MODDING[ModPage]"),
						LocalizedString.Id("Common.DIALOG_MESSAGE_MODDING[Disable]")
					});
					if (modInfo.loadError != null)
					{
						MessageDialog dialog = new MessageDialog(text3, message, LocalizedString.Value(modInfo.loadError.Replace("\\", "\\\\").Replace("*", "\\*")), copyButton: true, LocalizedString.Id("Common.OK"), otherActions);
						GameManager.instance.userInterface.appBindings.ShowMessageDialog(dialog, Callback);
					}
					else
					{
						MessageDialog dialog2 = new MessageDialog(text3, message, LocalizedString.Id("Common.OK"), otherActions);
						GameManager.instance.userInterface.appBindings.ShowMessageDialog(dialog2, Callback);
					}
				});
				void Callback(int msg)
				{
					switch (msg)
					{
					case 0:
						NotificationSystem.Pop(id);
						break;
					case 2:
						NotificationSystem.Pop(id);
						modInfo.asset.mod.onClick();
						break;
					case 3:
						NotificationSystem.Pop(id);
						modInfo.asset.mod.onEnable(obj: false);
						break;
					case 1:
						break;
					}
				}
			}
			LocalizedString value = ((m_ModsInfos.Count == 0) ? LocalizedString.Id(NotificationUISystem.GetText("ModsLoadingDoneZero")) : new LocalizedString(NotificationUISystem.GetText("ModsLoadingDone"), null, new Dictionary<string, ILocElement>
			{
				{
					"LOADED",
					new LocalizedNumber<int>(m_ModsInfos.Count - num, "integer")
				},
				{
					"TOTAL",
					new LocalizedNumber<int>(m_ModsInfos.Count, "integer")
				}
			}));
			text = value;
			progressState = ProgressState.Complete;
			NotificationSystem.Pop("ModLoadingStatus", 5f, null, text, "ModsLoading", null, null, progressState);
		}
		catch (Exception exception)
		{
			log.Error(exception);
			LocalizedString? text = LocalizedString.Id(NotificationUISystem.GetText("ModsLoadingAllFailed"));
			ProgressState? progressState = ProgressState.Failed;
			NotificationSystem.Pop("ModLoadingStatus", 5f, null, text, "ModsLoading", null, null, progressState);
		}
		finally
		{
			m_IsInProgress = false;
		}
	}
```

- `private InitializeMods(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
private void InitializeMods(UpdateSystem updateSystem)
	{
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.InfoFormat($"Mods initialized in {0}ms", t.TotalMilliseconds);
		}))
		{
			foreach (ModInfo modInfo in m_ModsInfos)
			{
				try
				{
					using (PerformanceCounter.Start(delegate(TimeSpan t)
					{
						log.InfoFormat($"Loaded {{1}} in {0}ms", t.TotalMilliseconds, modInfo.name);
					}))
					{
						modInfo.Load(updateSystem);
					}
				}
				catch (Exception exception)
				{
					modInfo.Dispose();
					log.ErrorFormat(exception, "Error initializing mod {0} ({1})", modInfo.name, modInfo.assemblyFullName);
				}
			}
		}
		InitializeUIModules();
	}
```

- `private InitializeUIModules() : System.Void`  

```csharp
private void InitializeUIModules()
	{
		UIModuleAsset[] array = AssetDatabase.global.GetAssets(default(SearchFilter<UIModuleAsset>)).ToArray();
		List<string> list = new List<string>();
		UIModuleAsset[] array2 = array;
		foreach (UIModuleAsset uIModuleAsset in array2)
		{
			if (uIModuleAsset.isEnabled)
			{
				UIManager.defaultUISystem.AddHostLocation("ui-mods", Path.GetDirectoryName(uIModuleAsset.path), uIModuleAsset.isLocal);
				log.InfoFormat("Registered UI Module {0} from {1}", uIModuleAsset.moduleInfo, uIModuleAsset);
				list.Add(uIModuleAsset.couiPath);
			}
		}
		GameManager.instance.userInterface.appBindings.AddActiveUIModLocation(list);
	}
```

- `public ListModsEnabled() : System.String[]`  

```csharp
public string[] ListModsEnabled()
	{
		return (from x in m_ModsInfos
			where x.isLoaded
			select x.name).Concat(from x in AssetDatabase.global.GetAssets(default(SearchFilter<UIModuleAsset>))
			select x.name).ToArray();
	}
```

- `private RegisterMods() : System.Void`  

```csharp
private void RegisterMods()
	{
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.InfoFormat("Mods registered in {0}ms", t.TotalMilliseconds);
		}))
		{
			m_ModsInfos.Clear();
			ExecutableAsset[] modAssets = ExecutableAsset.GetModAssets(typeof(IMod));
			foreach (ExecutableAsset executableAsset in modAssets)
			{
				try
				{
					m_ModsInfos.Add(new ModInfo(executableAsset));
				}
				catch (Exception exception)
				{
					log.ErrorFormat(exception, "Error registering mod {0}", executableAsset.fullName);
				}
			}
		}
	}
```

- `public RemoveUIModule(Colossal.IO.AssetDatabase.UIModuleAsset uiModule) : System.Void`  

```csharp
public void RemoveUIModule(UIModuleAsset uiModule)
	{
		if (m_Initialized)
		{
			UIManager.defaultUISystem.RemoveHostLocation("ui-mods", Path.GetDirectoryName(uiModule.path));
			GameManager.instance.userInterface.appBindings.RemoveActiveUIModLocation(new string[1] { uiModule.couiPath });
			log.InfoFormat("Unregistered UI Module {0}", uiModule.moduleInfo);
		}
	}
```

- `public RequireRestart() : System.Void`  

```csharp
public void RequireRestart()
	{
		if (!m_Initialized || restartRequired)
		{
			return;
		}
		restartRequired = true;
		log.Info("Restart required");
		ProgressState? progressState = ProgressState.Warning;
		NotificationSystem.Push("RestartRequired", null, null, "EnabledModsChanged", "EnabledModsChanged", null, progressState, null, delegate
		{
			ConfirmationDialog dialog = new ConfirmationDialog("Common.DIALOG_TITLE[Warning]", DialogMessage.GetId("EnabledModsChanged"), "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]");
			GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(dialog, delegate(int msg)
			{
				if (msg == 0)
				{
					restartRequired = false;
					GameManager.QuitGame();
				}
			});
		});
	}
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
public IEnumerator<ModInfo> GetEnumerator()
	{
		return m_ModsInfos.GetEnumerator();
	}
```

- `public TryGetExecutableAsset(Game.Modding.IMod mod, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  

```csharp
public bool TryGetExecutableAsset(Assembly assembly, out ExecutableAsset asset)
	{
		foreach (ModInfo modsInfo in m_ModsInfos)
		{
			if (modsInfo.asset.assembly == assembly)
			{
				asset = modsInfo.asset;
				return true;
			}
		}
		asset = null;
		return false;
	}
```

- `public TryGetExecutableAsset(System.Reflection.Assembly assembly, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  

```csharp
public bool TryGetExecutableAsset(Assembly assembly, out ExecutableAsset asset)
	{
		foreach (ModInfo modsInfo in m_ModsInfos)
		{
			if (modsInfo.asset.assembly == assembly)
			{
				asset = modsInfo.asset;
				return true;
			}
		}
		asset = null;
		return false;
	}
```


## Nested types

- `Game.Modding.ModManager+ModInfo`  
- `Game.Modding.ModManager+<>c`  
- `Game.Modding.ModManager+<>c__DisplayClass16_0`  
- `Game.Modding.ModManager+<>c__DisplayClass18_0`  
- `Game.Modding.ModManager+<>c__DisplayClass22_0`  

