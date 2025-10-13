# Game.Modding.Toolchain.Dependencies.CombinedDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public abstract class CombinedDependency : Game.Modding.Toolchain.IToolchainDependency
{
    private Game.Modding.Toolchain.IToolchainDependency+State m_State;
    private System.Version m_Version;
    private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
    private System.String <version>k__BackingField;
    private System.String <installationDirectory>k__BackingField;
    private System.Boolean <needDownload>k__BackingField;
    private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField;

    public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
    protected System.Boolean isAsync { protected get; }
    public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get; }
    public System.String name { get; }
    public Game.UI.Localization.LocalizedString localizedName { get; }
    public System.String version { get; protected set; }
    private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set; }
    public System.String icon { get; }
    public System.Boolean confirmUninstallation { get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public System.String installationDirectory { get; set; }
    public Game.UI.Localization.LocalizedString description { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
    public System.Boolean needDownload { get; protected set; }
    private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set; }
    public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set; }
    private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set; }
    private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get; }
    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }

    protected CombinedDependency();

    public System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Boolean> GetCombinedResult(System.Threading.CancellationToken token, System.Func<Game.Modding.Toolchain.IToolchainDependency, System.Threading.CancellationToken, System.Threading.Tasks.Task<System.Boolean>> getTaskPredicate);
    private System.Threading.Tasks.Task GetCombinedResult(Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType combineType, System.Threading.CancellationToken token, System.Func<Game.Modding.Toolchain.IToolchainDependency, System.Threading.CancellationToken, System.Threading.Tasks.Task> getTaskPredicate);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Refresh(System.Threading.CancellationToken token);
    public System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private Game.Modding.Toolchain.IToolchainDependency+State m_State`  

```csharp
private Game.Modding.Toolchain.IToolchainDependency+State m_State;
```

- `private System.Version m_Version`  

```csharp
private System.Version m_Version;
```

- `private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress`  

```csharp
private Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```

- `private System.String <version>k__BackingField`  

```csharp
private System.String <version>k__BackingField;
```

- `private System.String <installationDirectory>k__BackingField`  

```csharp
private System.String <installationDirectory>k__BackingField;
```

- `private System.Boolean <needDownload>k__BackingField`  

```csharp
private System.Boolean <needDownload>k__BackingField;
```

- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> <spaceRequirements>k__BackingField;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
```

- `protected System.Boolean isAsync { protected get }`  

```csharp
protected System.Boolean isAsync { protected get; }
```

- `public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get }`  

```csharp
public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Game.UI.Localization.LocalizedString localizedName { get }`  

```csharp
public Game.UI.Localization.LocalizedString localizedName { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```

- `private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set }`  

```csharp
private System.String Game.Modding.Toolchain.IToolchainDependency.version { private get; private set; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public System.Boolean confirmUninstallation { get }`  

```csharp
public System.Boolean confirmUninstallation { get; }
```

- `public System.Boolean canBeInstalled { get }`  

```csharp
public System.Boolean canBeInstalled { get; }
```

- `public System.Boolean canBeUninstalled { get }`  

```csharp
public System.Boolean canBeUninstalled { get; }
```

- `public System.Boolean canChangeInstallationDirectory { get }`  

```csharp
public System.Boolean canChangeInstallationDirectory { get; }
```

- `public System.String installationDirectory { get; set }`  

```csharp
public System.String installationDirectory { get; set; }
```

- `public Game.UI.Localization.LocalizedString description { get }`  

```csharp
public Game.UI.Localization.LocalizedString description { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```

- `public Game.Modding.Toolchain.IToolchainDependency+State state { get; set }`  

```csharp
public Game.Modding.Toolchain.IToolchainDependency+State state { get; set; }
```

- `public System.Boolean needDownload { get; protected set }`  

```csharp
public System.Boolean needDownload { get; protected set; }
```

- `private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set }`  

```csharp
private System.Boolean Game.Modding.Toolchain.IToolchainDependency.needDownload { private get; private set; }
```

- `public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set }`  

```csharp
public System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> spaceRequirements { get; protected set; }
```

- `private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements> Game.Modding.Toolchain.IToolchainDependency.spaceRequirements { private get; private set; }
```

- `private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> Game.Modding.Toolchain.IToolchainDependency.envVariables { private get; }
```

- `public System.Type[] dependsOnInstallation { get }`  

```csharp
public System.Type[] dependsOnInstallation { get; }
```

- `public System.Type[] dependsOnUninstallation { get }`  

```csharp
public System.Type[] dependsOnUninstallation { get; }
```


## Constructors

- `protected CombinedDependency()`  

```csharp
protected CombinedDependency();
```


## Methods

- `public Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Download(CancellationToken token)
	{
		return GetCombinedResult(type, token, (IToolchainDependency d, CancellationToken t) => d.Download(t));
	}
```

- `private GetCombinedResult(System.Threading.CancellationToken token, System.Func<Game.Modding.Toolchain.IToolchainDependency, System.Threading.CancellationToken, System.Threading.Tasks.Task<System.Boolean>> getTaskPredicate) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
private async Task GetCombinedResult(CombineType combineType, CancellationToken token, Func<IToolchainDependency, CancellationToken, Task> getTaskPredicate)
	{
		if (isAsync)
		{
			using (CancellationTokenSource anyTokenSource = new CancellationTokenSource())
			{
				CancellationTokenSource combinedTokenSource = CancellationTokenSource.CreateLinkedTokenSource(token, anyTokenSource.Token);
				try
				{
					List<Task> tasks = dependencies.Select((IToolchainDependency d) => getTaskPredicate(d, combinedTokenSource.Token)).ToList();
					switch (combineType)
					{
					case CombineType.OR:
					{
						List<Exception> errors = new List<Exception>();
						while (tasks.Count > 0)
						{
							Task task2 = await Task.WhenAny(tasks);
							tasks.Remove(task2);
							if (task2.IsCompletedSuccessfully)
							{
								anyTokenSource.Cancel();
								return;
							}
							if (task2.Exception != null)
							{
								errors.AddRange(task2.Exception.InnerExceptions);
							}
						}
						if (errors.Count != 0)
						{
							throw new AggregateException(errors);
						}
						return;
					}
					case CombineType.AND:
						while (tasks.Count > 0)
						{
							Task task = await Task.WhenAny(tasks);
							tasks.Remove(task);
							if (task.IsFaulted)
							{
								throw task.Exception;
							}
						}
						return;
					case CombineType.ALL:
						await Task.WhenAll(tasks);
						return;
					}
				}
				finally
				{
					if (combinedTokenSource != null)
					{
						((IDisposable)combinedTokenSource).Dispose();
					}
				}
			}
			return;
		}
		switch (combineType)
		{
		case CombineType.OR:
		{
			List<Exception> errors = new List<Exception>();
			foreach (IToolchainDependency dependency in dependencies)
			{
				Task task3 = getTaskPredicate(dependency, token);
				await task3;
				if (task3.IsCompletedSuccessfully)
				{
					return;
				}
				if (task3.Exception != null)
				{
					errors.AddRange(task3.Exception.InnerExceptions);
				}
			}
			if (errors.Count != 0)
			{
				throw new AggregateException(errors);
			}
			break;
		}
		case CombineType.AND:
			foreach (IToolchainDependency dependency2 in dependencies)
			{
				Task task3 = getTaskPredicate(dependency2, token);
				await task3;
				if (task3.IsFaulted)
				{
					throw task3.Exception;
				}
			}
			break;
		case CombineType.ALL:
			foreach (IToolchainDependency dependency3 in dependencies)
			{
				await getTaskPredicate(dependency3, token);
			}
			break;
		}
	}
```

- `private GetCombinedResult(Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType combineType, System.Threading.CancellationToken token, System.Func<Game.Modding.Toolchain.IToolchainDependency, System.Threading.CancellationToken, System.Threading.Tasks.Task> getTaskPredicate) : System.Threading.Tasks.Task`  

```csharp
private async Task GetCombinedResult(CombineType combineType, CancellationToken token, Func<IToolchainDependency, CancellationToken, Task> getTaskPredicate)
	{
		if (isAsync)
		{
			using (CancellationTokenSource anyTokenSource = new CancellationTokenSource())
			{
				CancellationTokenSource combinedTokenSource = CancellationTokenSource.CreateLinkedTokenSource(token, anyTokenSource.Token);
				try
				{
					List<Task> tasks = dependencies.Select((IToolchainDependency d) => getTaskPredicate(d, combinedTokenSource.Token)).ToList();
					switch (combineType)
					{
					case CombineType.OR:
					{
						List<Exception> errors = new List<Exception>();
						while (tasks.Count > 0)
						{
							Task task2 = await Task.WhenAny(tasks);
							tasks.Remove(task2);
							if (task2.IsCompletedSuccessfully)
							{
								anyTokenSource.Cancel();
								return;
							}
							if (task2.Exception != null)
							{
								errors.AddRange(task2.Exception.InnerExceptions);
							}
						}
						if (errors.Count != 0)
						{
							throw new AggregateException(errors);
						}
						return;
					}
					case CombineType.AND:
						while (tasks.Count > 0)
						{
							Task task = await Task.WhenAny(tasks);
							tasks.Remove(task);
							if (task.IsFaulted)
							{
								throw task.Exception;
							}
						}
						return;
					case CombineType.ALL:
						await Task.WhenAll(tasks);
						return;
					}
				}
				finally
				{
					if (combinedTokenSource != null)
					{
						((IDisposable)combinedTokenSource).Dispose();
					}
				}
			}
			return;
		}
		switch (combineType)
		{
		case CombineType.OR:
		{
			List<Exception> errors = new List<Exception>();
			foreach (IToolchainDependency dependency in dependencies)
			{
				Task task3 = getTaskPredicate(dependency, token);
				await task3;
				if (task3.IsCompletedSuccessfully)
				{
					return;
				}
				if (task3.Exception != null)
				{
					errors.AddRange(task3.Exception.InnerExceptions);
				}
			}
			if (errors.Count != 0)
			{
				throw new AggregateException(errors);
			}
			break;
		}
		case CombineType.AND:
			foreach (IToolchainDependency dependency2 in dependencies)
			{
				Task task3 = getTaskPredicate(dependency2, token);
				await task3;
				if (task3.IsFaulted)
				{
					throw task3.Exception;
				}
			}
			break;
		case CombineType.ALL:
			foreach (IToolchainDependency dependency3 in dependencies)
			{
				await getTaskPredicate(dependency3, token);
			}
			break;
		}
	}
```

- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public virtual LocalizedString GetLocalizedState(bool includeProgress)
	{
		return IToolchainDependency.GetLocalizedState(state, includeProgress);
	}
```

- `public GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public Task<List<IToolchainDependency.DiskSpaceRequirements>> GetRequiredDiskSpace(CancellationToken token)
	{
		return Task.FromResult(new List<IToolchainDependency.DiskSpaceRequirements>());
	}
```

- `public Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Install(CancellationToken token)
	{
		return GetCombinedResult(type, token, (IToolchainDependency d, CancellationToken t) => d.Install(t));
	}
```

- `public IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> IsInstalled(CancellationToken token)
	{
		return GetCombinedResult(token, (IToolchainDependency d, CancellationToken t) => d.IsInstalled(t));
	}
```

- `public IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> IsUpToDate(CancellationToken token)
	{
		return GetCombinedResult(token, (IToolchainDependency d, CancellationToken t) => d.IsUpToDate(t));
	}
```

- `public NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public Task<bool> NeedDownload(CancellationToken token)
	{
		return GetCombinedResult(token, (IToolchainDependency d, CancellationToken t) => d.NeedDownload(t));
	}
```

- `public virtual Refresh(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public virtual async Task Refresh(CancellationToken token)
	{
		await GetCombinedResult(CombineType.ALL, token, (IToolchainDependency d, CancellationToken t) => d.Refresh(t));
		await IToolchainDependency.Refresh(this, token);
	}
```

- `public Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public Task Uninstall(CancellationToken token)
	{
		return GetCombinedResult(type, token, (IToolchainDependency d, CancellationToken t) => d.Download(t));
	}
```


## Events

- `onNotifyProgress` : `Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate`  

```csharp
public event Game.Modding.Toolchain.IToolchainDependency+ProgressDelegate onNotifyProgress;
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<>c__DisplayClass68_0`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<>c__DisplayClass69_0`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<Game-Modding-Toolchain-IToolchainDependency-get_envVariables>d__63`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<GetCombinedResult>d__68`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<GetCombinedResult>d__69`  
- `Game.Modding.Toolchain.Dependencies.CombinedDependency+<Refresh>d__70`  

