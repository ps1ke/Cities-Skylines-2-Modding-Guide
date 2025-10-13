# Game.Modding.Toolchain.Dependencies.NpxModProjectDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class NpxModProjectDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private static readonly System.String kNpxPackagePath;
    private static const System.String kProjectName;
    private static const System.String kModuleNamespace;
    private static const System.String kModuleName;

    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
    public System.String name { get; }
    public System.String icon { get; }

    public NpxModProjectDependency();

    private static System.Threading.Tasks.Task DeleteNpxModule(System.String globalNodeModulePath, System.String moduleNamespace, System.String moduleName, System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.String> GetGlobalNodeModulePath(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private static readonly System.String kNpxPackagePath`  

```csharp
private static readonly System.String kNpxPackagePath;
```

- `private static const System.String kProjectName`  

```csharp
private static const System.String kProjectName;
```

- `private static const System.String kModuleNamespace`  

```csharp
private static const System.String kModuleNamespace;
```

- `private static const System.String kModuleName`  

```csharp
private static const System.String kModuleName;
```


## Properties

- `public System.Type[] dependsOnInstallation { get }`  

```csharp
public System.Type[] dependsOnInstallation { get; }
```

- `public System.Type[] dependsOnUninstallation { get }`  

```csharp
public System.Type[] dependsOnUninstallation { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```


## Constructors

- `public NpxModProjectDependency()`  

```csharp
public NpxModProjectDependency();
```


## Methods

- `private static DeleteNpxModule(System.String globalNodeModulePath, System.String moduleNamespace, System.String moduleName, System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
private static async Task DeleteNpxModule(string globalNodeModulePath, string moduleNamespace, string moduleName, CancellationToken token)
	{
		if (string.IsNullOrEmpty(globalNodeModulePath))
		{
			throw new ArgumentException("Directory path cannot be null or empty.", "globalNodeModulePath");
		}
		if (string.IsNullOrEmpty(moduleName))
		{
			throw new ArgumentException("File prefix cannot be null or empty.", "moduleName");
		}
		if (!Directory.Exists(globalNodeModulePath))
		{
			throw new DirectoryNotFoundException("The specified directory was not found: " + globalNodeModulePath);
		}
		string[] files = LongDirectory.GetFiles(globalNodeModulePath, moduleName + "*");
		string[] array = files;
		for (int i = 0; i < array.Length; i++)
		{
			await AsyncUtils.DeleteFileAsync(array[i], token).ConfigureAwait(continueOnCapturedContext: false);
		}
		await AsyncUtils.DeleteDirectoryAsync(Path.Combine(globalNodeModulePath, "node_modules", moduleNamespace), recursive: true, token).ConfigureAwait(continueOnCapturedContext: false);
	}
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override Task Download(CancellationToken token)
	{
		return Task.CompletedTask;
	}
```

- `private GetGlobalNodeModulePath(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
private async Task<string> GetGlobalNodeModulePath(CancellationToken token)
	{
		string path = string.Empty;
		List<string> errorText = new List<string>();
		try
		{
			await Cli.Wrap("npm").WithArguments("config get prefix").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				path = l;
			}))
				.WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
				{
					errorText.Add(l);
				}))
				.WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
		}
		catch (Win32Exception ex)
		{
			if (ex.ErrorCode != -2147467259)
			{
				IToolchainDependency.log.Error(ex, "Failed to get global npm module path");
			}
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.Error(exception, "Failed to get global npm module path");
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
		}
		return path;
	}
```

- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public override Task<List<IToolchainDependency.DiskSpaceRequirements>> GetRequiredDiskSpace(CancellationToken token)
	{
		return Task.FromResult(new List<IToolchainDependency.DiskSpaceRequirements>());
	}
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Install(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		List<string> output = new List<string>();
		List<string> errorText = new List<string>();
		try
		{
			IToolchainDependency.log.DebugFormat("Installing {0}", "UI Mod project template");
			base.state = new IToolchainDependency.State(DependencyState.Installing, "InstallingNpxModsTemplate");
			await Cli.Wrap("npm").WithArguments("link").WithWorkingDirectory(kNpxPackagePath)
				.WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
				{
					output.Add(l);
				}))
				.WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
				{
					errorText.Add(l);
				}))
				.WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.WarnFormat("{0}\n\n{1}", string.Join('\n', output), string.Join('\n', errorText));
			}
		}
		catch (OperationCanceledException)
		{
			throw;
		}
		catch (ToolchainException)
		{
			throw;
		}
		catch (Exception innerException)
		{
			throw new ToolchainException(ToolchainError.Install, this, innerException);
		}
	}
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override async Task<bool> IsInstalled(CancellationToken token)
	{
		string text = await GetGlobalNodeModulePath(token).ConfigureAwait(continueOnCapturedContext: false);
		if (LongDirectory.Exists(text))
		{
			return LongDirectory.Exists(Path.GetFullPath(Path.Combine(text, "node_modules", "@colossalorder")));
		}
		return false;
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override async Task<bool> IsUpToDate(CancellationToken token)
	{
		string text = await GetGlobalNodeModulePath(token).ConfigureAwait(continueOnCapturedContext: false);
		if (LongDirectory.Exists(text) && LongFile.TryGetSymlinkTarget(Path.Combine(text, "node_modules", "@colossalorder", "create-csii-ui-mod"), out var targetPath))
		{
			return targetPath == kNpxPackagePath;
		}
		return true;
	}
```

- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> NeedDownload(CancellationToken token)
	{
		return Task.FromResult(result: false);
	}
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Uninstall(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		try
		{
			IToolchainDependency.log.DebugFormat("Deleting {0}", "UI Mod project template");
			base.state = new IToolchainDependency.State(DependencyState.Removing, "RemovingNpxModsTemplate");
			string text = await GetGlobalNodeModulePath(token).ConfigureAwait(continueOnCapturedContext: false);
			if (LongDirectory.Exists(text))
			{
				await DeleteNpxModule(text, "@colossalorder", "create-csii-ui-mod", token);
			}
		}
		catch (OperationCanceledException)
		{
			throw;
		}
		catch (ToolchainException)
		{
			throw;
		}
		catch (Exception innerException)
		{
			throw new ToolchainException(ToolchainError.Uninstall, this, innerException);
		}
	}
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<>c__DisplayClass14_0`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<>c__DisplayClass19_0`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<DeleteNpxModule>d__20`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<GetGlobalNodeModulePath>d__14`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<Install>d__19`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<IsInstalled>d__15`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<IsUpToDate>d__16`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<Uninstall>d__21`  
- `Game.Modding.Toolchain.Dependencies.NpxModProjectDependency+<get_envVariables>d__6`  

