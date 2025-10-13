# Game.Modding.Toolchain.Dependencies.UnityModProjectDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class UnityModProjectDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    public static readonly System.String kProjectUnzipPath;
    public static readonly System.String kProjectZipPath;
    public static readonly System.String kModProjectsUnityVersionPath;
    public static readonly System.String kModProjectsVersionPath;
    public static readonly System.String kModProjectPackages;
    public static const System.String kProjectName;
    public static const System.String kProjectVersionTxt;
    public static const System.String kProjectSettingsAsset;
    public static const System.String kProjectPackageManifest;
    public static const System.String kProjectPackageLock;

    public static System.Boolean isUnityOpened { get; }
    public System.String name { get; }
    public System.String icon { get; }
    public System.String version { get; protected set; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
    public System.Type[] dependsOnInstallation { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }

    public UnityModProjectDependency();

    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    private static System.Boolean IsUnityOpenWithModsProject(System.String projectPath);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    private static Colossal.Version ReadUnityProjectVersion(System.String path);
    private static Colossal.Version ReadYAMLVersion(System.Collections.Generic.IEnumerable<System.String> lines);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `public static readonly System.String kProjectUnzipPath`  

```csharp
public static readonly System.String kProjectUnzipPath;
```

- `public static readonly System.String kProjectZipPath`  

```csharp
public static readonly System.String kProjectZipPath;
```

- `public static readonly System.String kModProjectsUnityVersionPath`  

```csharp
public static readonly System.String kModProjectsUnityVersionPath;
```

- `public static readonly System.String kModProjectsVersionPath`  

```csharp
public static readonly System.String kModProjectsVersionPath;
```

- `public static readonly System.String kModProjectPackages`  

```csharp
public static readonly System.String kModProjectPackages;
```

- `public static const System.String kProjectName`  

```csharp
public static const System.String kProjectName;
```

- `public static const System.String kProjectVersionTxt`  

```csharp
public static const System.String kProjectVersionTxt;
```

- `public static const System.String kProjectSettingsAsset`  

```csharp
public static const System.String kProjectSettingsAsset;
```

- `public static const System.String kProjectPackageManifest`  

```csharp
public static const System.String kProjectPackageManifest;
```

- `public static const System.String kProjectPackageLock`  

```csharp
public static const System.String kProjectPackageLock;
```


## Properties

- `public static System.Boolean isUnityOpened { get }`  

```csharp
public static System.Boolean isUnityOpened { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```

- `public System.Collections.Generic.IEnumerable<System.String> envVariables { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }
```

- `public System.Type[] dependsOnInstallation { get }`  

```csharp
public System.Type[] dependsOnInstallation { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```


## Constructors

- `public UnityModProjectDependency()`  

```csharp
public UnityModProjectDependency();
```


## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override Task Download(CancellationToken token)
	{
		return Task.CompletedTask;
	}
```

- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public override Task<List<IToolchainDependency.DiskSpaceRequirements>> GetRequiredDiskSpace(CancellationToken token)
	{
		return Task.FromResult(new List<IToolchainDependency.DiskSpaceRequirements>
		{
			new IToolchainDependency.DiskSpaceRequirements
			{
				m_Path = kProjectUnzipPath,
				m_Size = 1073741824L
			}
		});
	}
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Install(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		string zipPath = kProjectZipPath;
		string unzipPath = kProjectUnzipPath;
		try
		{
			if (isUnityOpened)
			{
				IToolchainDependency.log.Debug("Waiting for close Unity");
				base.state = new IToolchainDependency.State(DependencyState.Installing, "WaitingUnityClose");
				await AsyncUtils.WaitForAction(() => !isUnityOpened, token).ConfigureAwait(continueOnCapturedContext: false);
			}
			token.ThrowIfCancellationRequested();
			IToolchainDependency.log.DebugFormat("Deploy Mods project from '{0}' to '{1}'", zipPath, unzipPath);
			base.state = new IToolchainDependency.State(DependencyState.Installing, "InstallingModProject");
			if (LongDirectory.Exists(unzipPath))
			{
				await AsyncUtils.DeleteDirectoryAsync(unzipPath, recursive: true, token).ConfigureAwait(continueOnCapturedContext: false);
			}
			await Task.Run(delegate
			{
				ZipUtilities.Unzip(zipPath, unzipPath);
			}, token).ConfigureAwait(continueOnCapturedContext: false);
			IToolchainDependency.log.DebugFormat("Launching Unity ({0})", UnityDependency.unityExe);
			CliWrap.Command command = Cli.Wrap(UnityDependency.unityExe).WithArguments(new string[5] { "-projectPath", unzipPath, "-logFile", "-", "-quit" });
			await foreach (CommandEvent item in command.ListenAsync(token).ConfigureAwait(continueOnCapturedContext: false))
			{
				if (!(item is StandardOutputCommandEvent standardOutputCommandEvent))
				{
					if (item is StandardErrorCommandEvent standardErrorCommandEvent)
					{
						IToolchainDependency.log.Error(standardErrorCommandEvent.Text);
					}
				}
				else
				{
					IToolchainDependency.log.Debug(standardOutputCommandEvent.Text);
				}
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
public override Task<bool> IsInstalled(CancellationToken token)
	{
		return Task.FromResult(LongDirectory.Exists(kProjectUnzipPath + "/Library") && LongFile.Exists(kModProjectsUnityVersionPath));
	}
```

- `private static IsUnityOpenWithModsProject(System.String projectPath) : System.Boolean`  

```csharp
private static bool IsUnityOpenWithModsProject(string projectPath)
	{
		try
		{
			Process[] processesByName = Process.GetProcessesByName("unity");
			for (int i = 0; i < processesByName.Length; i++)
			{
				string parameterValue;
				int num = ProcessCommandLine.Retrieve(processesByName[i], out parameterValue);
				if (num == 0)
				{
					string openProjectPath = string.Empty;
					new OptionSet().Add("projectpath=", "", delegate(string option)
					{
						openProjectPath = option;
					}).Parse(ProcessCommandLine.CommandLineToArgs(parameterValue));
					if (!string.IsNullOrEmpty(openProjectPath) && Path.GetFullPath(openProjectPath) == Path.GetFullPath(projectPath))
					{
						return true;
					}
				}
				else
				{
					IToolchainDependency.log.DebugFormat("Unable to get command line ({0}): {1}", num, ProcessCommandLine.ErrorToString(num));
				}
			}
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.Warn(exception);
		}
		return false;
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> IsUpToDate(CancellationToken token)
	{
		try
		{
			Colossal.Version obj = ReadUnityProjectVersion(kModProjectsUnityVersionPath);
			Colossal.Version version = new Colossal.Version(UnityDependency.sUnityVersion);
			Colossal.Version version2 = ReadYAMLVersion(LongFile.ReadAllLines(kModProjectsVersionPath));
			Colossal.Version version3 = ReadYAMLVersion(ZipUtilities.ExtractAllLines(kProjectZipPath, "ProjectSettings/ProjectSettings.asset"));
			if (obj < version || version2 < version3)
			{
				return Task.FromResult(result: false);
			}
			if (!LongFile.Exists(kModProjectPackages))
			{
				return Task.FromResult(result: false);
			}
			Variant variant = JSON.Load(LongFile.ReadAllText(kModProjectPackages));
			Variant variant2 = JSON.Load(ZipUtilities.ExtractAllText(kProjectZipPath, "Packages/manifest.json"));
			ProxyObject proxyObject = variant.TryGet("dependencies") as ProxyObject;
			ProxyObject proxyObject2 = variant2.TryGet("dependencies") as ProxyObject;
			if (proxyObject == null || proxyObject2 == null)
			{
				return Task.FromResult(result: false);
			}
			foreach (KeyValuePair<string, Variant> item in (IEnumerable<KeyValuePair<string, Variant>>)proxyObject2)
			{
				if (!proxyObject.TryGetValue(item.Key, out var variant3))
				{
					return Task.FromResult(result: false);
				}
				if (!(variant3 is ProxyObject proxyObject3))
				{
					return Task.FromResult(result: false);
				}
				if (!proxyObject3.TryGetValue("version", out var variant4) || !variant4.Equals(item.Value))
				{
					return Task.FromResult(result: false);
				}
			}
			return Task.FromResult(result: true);
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.Error(exception, "Error during up-to-date check");
			return Task.FromResult(result: false);
		}
	}
```

- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> NeedDownload(CancellationToken token)
	{
		return Task.FromResult(result: false);
	}
```

- `private static ReadUnityProjectVersion(System.String path) : Colossal.Version`  

```csharp
private static Colossal.Version ReadUnityProjectVersion(string path)
	{
		return new Colossal.Version(LongFile.ReadAllLines(path)[0].Split(':')[1].Trim());
	}
```

- `private static ReadYAMLVersion(System.Collections.Generic.IEnumerable<System.String> lines) : Colossal.Version`  

```csharp
private static Colossal.Version ReadYAMLVersion(IEnumerable<string> lines)
	{
		foreach (string line in lines)
		{
			if (line.Contains("bundleVersion:"))
			{
				return new Colossal.Version(line.Split(':')[1].Trim());
			}
		}
		throw new Exception();
	}
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Uninstall(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		try
		{
			IToolchainDependency.log.Debug("Deleting Mods project");
			base.state = new IToolchainDependency.State(DependencyState.Installing, "RemovingModProject");
			string text = kProjectUnzipPath;
			if (LongDirectory.Exists(text))
			{
				await AsyncUtils.DeleteDirectoryAsync(text, recursive: true, token).ConfigureAwait(continueOnCapturedContext: false);
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

- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c__DisplayClass29_0`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<>c__DisplayClass34_0`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<Install>d__29`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<Uninstall>d__30`  
- `Game.Modding.Toolchain.Dependencies.UnityModProjectDependency+<get_envVariables>d__20`  

