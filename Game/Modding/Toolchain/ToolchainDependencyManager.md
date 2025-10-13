# Game.Modding.Toolchain.ToolchainDependencyManager

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class ToolchainDependencyManager : System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency>, System.Collections.IEnumerable
{
    private System.Boolean <isInProgress>k__BackingField;
    private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged;
    private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies;
    public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State;
    public static readonly System.String kUserToolingPath;
    public static readonly System.String kGameToolingPath;
    public static readonly Colossal.Logging.ILog log;
    public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency;
    private static const System.String kToolchain;
    private static const System.String kInstallingToolchain;
    private static const System.String kUninstallingToolchain;
    private static const System.String kInstallingToolchainFailed;
    private static const System.String kUninstallingToolchainFailed;
    private static const System.String kInstalledKey;
    private static const System.String kInstalledValue;

    public System.Boolean isInProgress { get; private set; }
    public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
    public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set; }
    private static System.Boolean isInstalled { private get; private set; }

    public ToolchainDependencyManager();

    private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> <GetCurrentState>b__25_0();
    internal static System.Void <Install>g__ProcessException|33_1(System.Exception ex);
    internal static System.Void <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex);
    internal static System.Void <Install>g__SetFailedNotification|33_2();
    internal static System.Void <Uninstall>g__ProcessException|34_1(System.Exception ex);
    internal static System.Void <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex);
    internal static System.Void <Uninstall>g__SetFailedNotification|34_2();
    private static System.Boolean CheckFreeSpace(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> requirements, System.String& message);
    public System.Threading.Tasks.Task<Game.Modding.Toolchain.ToolchainDependencyManager+State> GetCurrentState();
    private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> GetDeploymentState(System.Threading.CancellationToken token, System.Boolean forceRefresh, System.Boolean throwException);
    public System.Collections.Generic.IEnumerator<Game.Modding.Toolchain.IToolchainDependency> GetEnumerator();
    public System.Threading.Tasks.Task Install(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToInstall, System.Threading.CancellationToken token);
    private static System.Void OpenOptions();
    public System.Void Register<T>();
    private System.Void SetProgress(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State dependencyState);
    private static System.Void ShowErrorDialog(Game.UI.Localization.LocalizedString message, System.Exception ex);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Threading.Tasks.Task Uninstall(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToUninstall, System.Threading.CancellationToken token);
}
```


## Fields

- `private System.Boolean <isInProgress>k__BackingField`  

```csharp
private System.Boolean <isInProgress>k__BackingField;
```

- `private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged`  

```csharp
private System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged;
```

- `private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies`  

```csharp
private readonly System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> m_Dependencies;
```

- `public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State m_State;
```

- `public static readonly System.String kUserToolingPath`  

```csharp
public static readonly System.String kUserToolingPath;
```

- `public static readonly System.String kGameToolingPath`  

```csharp
public static readonly System.String kGameToolingPath;
```

- `public static readonly Colossal.Logging.ILog log`  

```csharp
public static readonly Colossal.Logging.ILog log;
```

- `public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency`  

```csharp
public static readonly Game.Modding.Toolchain.Dependencies.MainDependency m_MainDependency;
```

- `private static const System.String kToolchain`  

```csharp
private static const System.String kToolchain;
```

- `private static const System.String kInstallingToolchain`  

```csharp
private static const System.String kInstallingToolchain;
```

- `private static const System.String kUninstallingToolchain`  

```csharp
private static const System.String kUninstallingToolchain;
```

- `private static const System.String kInstallingToolchainFailed`  

```csharp
private static const System.String kInstallingToolchainFailed;
```

- `private static const System.String kUninstallingToolchainFailed`  

```csharp
private static const System.String kUninstallingToolchainFailed;
```

- `private static const System.String kInstalledKey`  

```csharp
private static const System.String kInstalledKey;
```

- `private static const System.String kInstalledValue`  

```csharp
private static const System.String kInstalledValue;
```


## Properties

- `public System.Boolean isInProgress { get; private set }`  

```csharp
public System.Boolean isInProgress { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
```

- `public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set }`  

```csharp
public Game.Modding.Toolchain.ToolchainDependencyManager+State cachedState { get; set; }
```

- `private static System.Boolean isInstalled { private get; private set }`  

```csharp
private static System.Boolean isInstalled { private get; private set; }
```


## Constructors

- `public ToolchainDependencyManager()`  

```csharp
public ToolchainDependencyManager();
```


## Methods

- `private <GetCurrentState>b__25_0() : System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState>`  

```csharp
private System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState> <GetCurrentState>b__25_0();
```

- `internal static <Install>g__ProcessException|33_1(System.Exception ex) : System.Void`  

```csharp
internal static System.Void <Install>g__ProcessException|33_1(System.Exception ex);
```

- `internal static <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex) : System.Void`  

```csharp
internal static System.Void <Install>g__ProcessToolchainException|33_0(Game.Modding.Toolchain.ToolchainException ex);
```

- `internal static <Install>g__SetFailedNotification|33_2() : System.Void`  

```csharp
internal static System.Void <Install>g__SetFailedNotification|33_2();
```

- `internal static <Uninstall>g__ProcessException|34_1(System.Exception ex) : System.Void`  

```csharp
internal static System.Void <Uninstall>g__ProcessException|34_1(System.Exception ex);
```

- `internal static <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex) : System.Void`  

```csharp
internal static System.Void <Uninstall>g__ProcessToolchainException|34_0(Game.Modding.Toolchain.ToolchainException ex);
```

- `internal static <Uninstall>g__SetFailedNotification|34_2() : System.Void`  

```csharp
internal static System.Void <Uninstall>g__SetFailedNotification|34_2();
```

- `private static CheckFreeSpace(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> requirements, System.String& message) : System.Boolean`  

```csharp
private static bool CheckFreeSpace(List<IToolchainDependency.DiskSpaceRequirements> requirements, out string message)
	{
		Dictionary<string, long> dictionary = new Dictionary<string, long>();
		foreach (IToolchainDependency.DiskSpaceRequirements requirement in requirements)
		{
			string pathRoot = Path.GetPathRoot(Path.GetFullPath(requirement.m_Path));
			if (!dictionary.ContainsKey(pathRoot))
			{
				dictionary[pathRoot] = 0L;
			}
			dictionary[pathRoot] += requirement.m_Size;
		}
		List<string> list = new List<string>();
		foreach (KeyValuePair<string, long> item in dictionary)
		{
			IOUtils.GetStorageStatus(item.Key, out var _, out var available);
			if (available < item.Value)
			{
				if (item.Value < 1000)
				{
					list.Add($"Disk {item.Key[0]}: {item.Value}B");
				}
				else if (item.Value < 1000000)
				{
					list.Add($"Disk {item.Key[0]}: {math.ceil((float)item.Value / 100f) / 10f:F1}KB");
				}
				else if (item.Value < 1000000000)
				{
					list.Add($"Disk {item.Key[0]}: {math.ceil((float)item.Value / 100000f) / 10f:F1}MB");
				}
				else
				{
					list.Add($"Disk {item.Key[0]}: {math.ceil((float)item.Value / 100000000f) / 10f:F1}GB");
				}
			}
		}
		message = string.Join("\n", list);
		return list.Count == 0;
	}
```

- `public GetCurrentState() : System.Threading.Tasks.Task<Game.Modding.Toolchain.ToolchainDependencyManager+State>`  

```csharp
public async Task<State> GetCurrentState()
	{
		DeploymentState state = await Task.Run(async () => await GetDeploymentState(GameManager.instance.terminationToken, forceRefresh: true));
		cachedState = cachedState.WithState(state);
		return cachedState;
	}
```

- `private GetDeploymentState(System.Threading.CancellationToken token, System.Boolean forceRefresh = False, System.Boolean throwException = True) : System.Threading.Tasks.Task<Game.Modding.Toolchain.DeploymentState>`  

```csharp
private async Task<DeploymentState> GetDeploymentState(CancellationToken token, bool forceRefresh = false, bool throwException = true)
	{
		try
		{
			token.ThrowIfCancellationRequested();
			bool isAnyDependencyOutdated = false;
			bool isAnyDependencyNotInstalled = false;
			IToolchainDependency.UpdateProcessEnvVarPathValue();
			IEnumerable<IToolchainDependency> source;
			if (!forceRefresh)
			{
				source = m_Dependencies.Where((IToolchainDependency d) => (DependencyState)d.state == DependencyState.Unknown);
			}
			else
			{
				IEnumerable<IToolchainDependency> enumerable = m_Dependencies;
				source = enumerable;
			}
			await Task.WhenAll(source.Select((IToolchainDependency d) => d.Refresh(token)));
			using (List<IToolchainDependency>.Enumerator enumerator = m_Dependencies.GetEnumerator())
			{
				while (enumerator.MoveNext())
				{
					switch (enumerator.Current.state.m_State)
					{
					case DependencyState.Outdated:
						isAnyDependencyOutdated = true;
						break;
					case DependencyState.NotInstalled:
						isAnyDependencyNotInstalled = true;
						break;
					}
				}
			}
			if (!isInstalled)
			{
				return DeploymentState.NotInstalled;
			}
			if (isAnyDependencyNotInstalled)
			{
				return DeploymentState.Invalid;
			}
			if (isAnyDependencyOutdated)
			{
				return DeploymentState.Outdated;
			}
			return DeploymentState.Installed;
		}
		catch (OperationCanceledException)
		{
			return DeploymentState.Unknown;
		}
		catch (Exception exception)
		{
			log.Warn(exception, "Exception occured during GetDeploymentState");
			if (throwException)
			{
				throw;
			}
			return DeploymentState.Unknown;
		}
	}
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Game.Modding.Toolchain.IToolchainDependency>`  

```csharp
public IEnumerator<IToolchainDependency> GetEnumerator()
	{
		return m_Dependencies.GetEnumerator();
	}
```

- `public Install(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToInstall, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public async Task Install(List<IToolchainDependency> dependenciesToInstall, CancellationToken token)
	{
		if (isInProgress)
		{
			return;
		}
		try
		{
			_ = 3;
			try
			{
				isInProgress = true;
				log.Info("Start modding toolchain installation");
				ProgressState? progressState = ProgressState.Indeterminate;
				Action onClicked = OpenOptions;
				NotificationSystem.Push("Toolchain", null, null, "Toolchain", "InstallingToolchain", null, progressState, null, onClicked);
				cachedState = cachedState.WithStatus(ModdingToolStatus.Installing).WithState(await GetDeploymentState(token)).WithStages(dependenciesToInstall.Count((IToolchainDependency d) => d.state.m_State != DependencyState.Installed))
					.WithProgress(null);
				dependenciesToInstall.Sort(IToolchainDependency.InstallSorting);
				List<IToolchainDependency.DiskSpaceRequirements> list = new List<IToolchainDependency.DiskSpaceRequirements>();
				foreach (IToolchainDependency item in dependenciesToInstall)
				{
					list.AddRange(item.spaceRequirements);
				}
				if (!CheckFreeSpace(list, out var message))
				{
					throw new ToolchainException(ToolchainError.NotEnoughSpace, null, message);
				}
				foreach (IToolchainDependency item2 in dependenciesToInstall)
				{
					item2.state = (IToolchainDependency.State)DependencyState.Queued;
				}
				foreach (IToolchainDependency dependency in dependenciesToInstall)
				{
					cachedState = cachedState.WithNextStage();
					dependency.onNotifyProgress += SetProgress;
					if (dependency.needDownload)
					{
						dependency.state = (IToolchainDependency.State)DependencyState.Downloading;
						await dependency.Download(token);
					}
					dependency.state = (IToolchainDependency.State)DependencyState.Installing;
					await dependency.Install(token);
					dependency.onNotifyProgress -= SetProgress;
					UserEnvironmentVariableManager.SetEnvVars(dependency.envVariables.ToArray());
					await dependency.Refresh(token);
				}
				isInstalled = true;
				progressState = ProgressState.Complete;
				NotificationSystem.Pop("Toolchain", 1f, null, null, "Toolchain", "InstallingToolchain", null, progressState);
			}
			catch (OperationCanceledException)
			{
				log.Info("Installation canceled");
				SetFailedNotification();
			}
			catch (AggregateException ex2)
			{
				foreach (Exception innerException in ex2.InnerExceptions)
				{
					if (innerException is ToolchainException ex3)
					{
						ProcessToolchainException(ex3);
					}
					else
					{
						ProcessException(innerException);
					}
				}
				SetFailedNotification();
			}
			catch (ToolchainException ex4)
			{
				ProcessToolchainException(ex4);
				SetFailedNotification();
			}
			catch (Exception ex5)
			{
				ProcessException(ex5);
				SetFailedNotification();
			}
		}
		finally
		{
			cachedState = cachedState.WithStatus(ModdingToolStatus.Idle).WithState(await GetDeploymentState(token, forceRefresh: true, throwException: false)).WithStages(0)
				.WithProgress(null);
			isInProgress = false;
		}
		static void ProcessException(Exception ex6)
		{
			log.Error(ex6, "Unknown error while modding toolchain installation");
			ShowErrorDialog(LocalizedString.Id("Options.ERROR_TOOLCHAIN_INSTALL_UNKNOWN"), ex6);
		}
		static void ProcessToolchainException(ToolchainException ex6)
		{
			switch (ex6.error)
			{
			case ToolchainError.Download:
				log.Error(ex6.InnerException, $"Error while downloading dependency \"{ex6.source.localizedName}\": {ex6.Message}");
				ShowErrorDialog(new LocalizedString(string.IsNullOrEmpty(ex6.Message) ? "Options.ERROR_TOOLCHAIN_DEPENDENCY_DOWNLOAD" : "Options.ERROR_TOOLCHAIN_DEPENDENCY_DOWNLOAD_DETAILS", null, new Dictionary<string, ILocElement>
				{
					{
						"DEPENDENCY_NAME",
						ex6.source.localizedName
					},
					{
						"DETAILS",
						LocalizedString.Value(ex6.Message)
					}
				}), ex6.InnerException);
				break;
			case ToolchainError.Install:
				log.Error(ex6.InnerException, $"Error while installing dependency \"{ex6.source}\": {ex6.Message}");
				ShowErrorDialog(new LocalizedString(string.IsNullOrEmpty(ex6.Message) ? "Options.ERROR_TOOLCHAIN_DEPENDENCY_INSTALL" : "Options.ERROR_TOOLCHAIN_DEPENDENCY_INSTALL_DETAILS", null, new Dictionary<string, ILocElement>
				{
					{
						"DEPENDENCY_NAME",
						ex6.source.localizedName
					},
					{
						"DETAILS",
						LocalizedString.Value(ex6.Message)
					}
				}), ex6.InnerException);
				break;
			case ToolchainError.NotEnoughSpace:
				log.Error((Exception)null, (object)("Not enough space on disk to install modding toolchain:\n" + ex6.Message));
				ShowErrorDialog(new LocalizedString(string.IsNullOrEmpty(ex6.Message) ? "Options.ERROR_TOOLCHAIN_NO_SPACE" : "Options.ERROR_TOOLCHAIN_NO_SPACE_DETAILS", null, new Dictionary<string, ILocElement> { 
				{
					"DETAILS",
					LocalizedString.Value(ex6.Message)
				} }));
				break;
			}
		}
		static void SetFailedNotification()
		{
			ProgressState? progressState2 = ProgressState.Failed;
			NotificationSystem.Pop("Toolchain", 5f, null, null, null, "InstallingToolchainFailed", null, progressState2);
		}
	}
```

- `private static OpenOptions() : System.Void`  

```csharp
private static void OpenOptions()
	{
		World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<OptionsUISystem>()?.OpenPage("Modding", "General", isAdvanced: false);
	}
```

- `public Register<T>() : System.Void`  

```csharp
public System.Void Register<T>();
```

- `private SetProgress(Game.Modding.Toolchain.IToolchainDependency dependency, Game.Modding.Toolchain.IToolchainDependency+State dependencyState) : System.Void`  

```csharp
private void SetProgress(IToolchainDependency dependency, IToolchainDependency.State dependencyState)
	{
		cachedState = cachedState.WithProgress(dependencyState.m_Progress, dependencyState.m_Details);
	}
```

- `private static ShowErrorDialog(Game.UI.Localization.LocalizedString message, System.Exception ex = null) : System.Void`  

```csharp
private static void ShowErrorDialog(LocalizedString message, Exception ex = null)
	{
		ErrorDialogManager.ShowErrorDialog(new ErrorDialog
		{
			localizedTitle = LocalizedString.Id("Options.ERROR_TOOLCHAIN"),
			localizedMessage = message,
			actions = ErrorDialog.Actions.None,
			severity = ErrorDialog.Severity.Error,
			errorDetails = ((ex != null) ? StackTraceHelper.ExtractStackTraceFromException(ex) : null)
		});
	}
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
public IEnumerator<IToolchainDependency> GetEnumerator()
	{
		return m_Dependencies.GetEnumerator();
	}
```

- `public Uninstall(System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependenciesToUninstall, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public async Task Uninstall(List<IToolchainDependency> dependenciesToUninstall, CancellationToken token)
	{
		if (isInProgress)
		{
			return;
		}
		try
		{
			_ = 3;
			try
			{
				isInProgress = true;
				log.Info("Start modding toolchain uninstallation");
				ProgressState? progressState = ProgressState.Indeterminate;
				Action onClicked = OpenOptions;
				NotificationSystem.Push("Toolchain", null, null, "Toolchain", "UninstallingToolchain", null, progressState, null, onClicked);
				cachedState = cachedState.WithStatus(ModdingToolStatus.Uninstalling).WithState(await GetDeploymentState(token)).WithStages(dependenciesToUninstall.Count((IToolchainDependency d) => d.state.m_State != DependencyState.NotInstalled))
					.WithProgress(null);
				dependenciesToUninstall.Sort(IToolchainDependency.UninstallSorting);
				foreach (IToolchainDependency item in dependenciesToUninstall)
				{
					item.state = (IToolchainDependency.State)DependencyState.Queued;
				}
				foreach (IToolchainDependency dependency in dependenciesToUninstall)
				{
					cachedState = cachedState.WithNextStage();
					dependency.onNotifyProgress += SetProgress;
					bool flag = !dependency.confirmUninstallation;
					if (!flag)
					{
						TaskCompletionSource<bool> tcs = new TaskCompletionSource<bool>();
						LocalizedString message = dependency.uninstallMessage;
						if (message.Equals(default(LocalizedString)))
						{
							message = new LocalizedString("Options.WARN_TOOLCHAIN_DEPENDENCY_UNINSTALL", null, new Dictionary<string, ILocElement> { { "DEPENDENCY_NAME", dependency.localizedName } });
						}
						ConfirmationDialog dialog = new ConfirmationDialog("Common.DIALOG_TITLE[Warning]", message, "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]");
						GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(dialog, delegate(int msg)
						{
							tcs.SetResult(msg == 0);
						});
						flag = await tcs.Task;
					}
					if (flag)
					{
						dependency.state = (IToolchainDependency.State)DependencyState.Removing;
						await dependency.Uninstall(token);
					}
					dependency.onNotifyProgress -= SetProgress;
					await dependency.Refresh(token);
				}
				UserEnvironmentVariableManager.RemoveEnvVars(dependencies.Where((IToolchainDependency d) => d.state.m_State != DependencyState.NotInstalled).SelectMany((IToolchainDependency d) => d.envVariables).Distinct()
					.ToArray());
				progressState = ProgressState.Complete;
				NotificationSystem.Pop("Toolchain", 1f, null, null, "Toolchain", "UninstallingToolchain", null, progressState);
			}
			catch (OperationCanceledException)
			{
				log.Info("Uninstallation canceled");
				SetFailedNotification();
			}
			catch (AggregateException ex2)
			{
				foreach (Exception innerException in ex2.InnerExceptions)
				{
					if (innerException is ToolchainException ex3)
					{
						ProcessToolchainException(ex3);
					}
					else
					{
						ProcessException(innerException);
					}
				}
				SetFailedNotification();
			}
			catch (ToolchainException ex4)
			{
				ProcessToolchainException(ex4);
				SetFailedNotification();
			}
			catch (Exception ex5)
			{
				ProcessException(ex5);
				SetFailedNotification();
			}
		}
		finally
		{
			cachedState = cachedState.WithStatus(ModdingToolStatus.Idle).WithState(await GetDeploymentState(token, forceRefresh: true, throwException: false)).WithStages(0)
				.WithProgress(null);
			isInProgress = false;
		}
		static void ProcessException(Exception ex6)
		{
			log.Error(ex6, "Unknown error while modding toolchain uninstallation");
			ShowErrorDialog(LocalizedString.Id("Options.ERROR_TOOLCHAIN_UNINSTALL_UNKNOWN"), ex6);
		}
		static void ProcessToolchainException(ToolchainException ex6)
		{
			log.Error(ex6.InnerException, $"Error while uninstalling dependency \"{ex6.source}\": {ex6.Message}");
			ShowErrorDialog(new LocalizedString(string.IsNullOrEmpty(ex6.Message) ? "Options.ERROR_TOOLCHAIN_DEPENDENCY_UNINSTALL" : "Options.ERROR_TOOLCHAIN_DEPENDENCY_UNINSTALL_DETAILS", null, new Dictionary<string, ILocElement>
			{
				{
					"DEPENDENCY_NAME",
					ex6.source.localizedName
				},
				{
					"DETAILS",
					LocalizedString.Value(ex6.Message)
				}
			}), ex6.InnerException);
		}
		static void SetFailedNotification()
		{
			ProgressState? progressState2 = ProgressState.Failed;
			NotificationSystem.Pop("Toolchain", 5f, null, null, null, "InstallingToolchainFailed", null, progressState2);
		}
	}
```


## Events

- `OnStateChanged` : `System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State>`  

```csharp
public event System.Action<Game.Modding.Toolchain.ToolchainDependencyManager+State> OnStateChanged;
```


## Nested types

- `Game.Modding.Toolchain.ToolchainDependencyManager+UserEnvironmentVariableManager`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+State`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+DependencyFilter`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+FilterResult`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<<GetCurrentState>b__25_0>d`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<>c`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<>c__DisplayClass34_0`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<>c__DisplayClass38_0`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<GetCurrentState>d__25`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<GetDeploymentState>d__38`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<Install>d__33`  
- `Game.Modding.Toolchain.ToolchainDependencyManager+<Uninstall>d__34`  

