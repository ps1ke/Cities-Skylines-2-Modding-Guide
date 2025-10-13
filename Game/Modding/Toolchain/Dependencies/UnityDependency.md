# Game.Modding.Toolchain.Dependencies.UnityDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class UnityDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private System.Nullable<System.Int64> m_DownloadSize;
    private System.String m_InstallationDirectory;
    public static readonly System.String sUnityVersion;
    public static readonly System.String kDefaultInstallationDirectory;
    public static readonly System.String kInstallationFolder;
    private static System.String sUnityPath;
    public static const System.String kUnityInstallerUrl;

    public System.String name { get; }
    public System.String icon { get; }
    public System.String version { get; protected set; }
    public static System.String unityPath { get; }
    public static System.String unityExe { get; }
    public static System.String unityUninstallerExe { get; }
    public System.String installerPath { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public System.Boolean confirmUninstallation { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }

    public UnityDependency();

    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Int64> GetUnityInstallerSize(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    private static System.Boolean TryGetParentPath(System.String path, System.Int32 depth, System.String& parentPath);
    private static System.Boolean TryGetRegistryKeyValue(Microsoft.Win32.RegistryKey registry, System.String path, System.String key, System.String& value);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private System.Nullable<System.Int64> m_DownloadSize`  

```csharp
private System.Nullable<System.Int64> m_DownloadSize;
```

- `private System.String m_InstallationDirectory`  

```csharp
private System.String m_InstallationDirectory;
```

- `public static readonly System.String sUnityVersion`  

```csharp
public static readonly System.String sUnityVersion;
```

- `public static readonly System.String kDefaultInstallationDirectory`  

```csharp
public static readonly System.String kDefaultInstallationDirectory;
```

- `public static readonly System.String kInstallationFolder`  

```csharp
public static readonly System.String kInstallationFolder;
```

- `private static System.String sUnityPath`  

```csharp
private static System.String sUnityPath;
```

- `public static const System.String kUnityInstallerUrl`  

```csharp
public static const System.String kUnityInstallerUrl;
```


## Properties

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

- `public static System.String unityPath { get }`  

```csharp
public static System.String unityPath { get; }
```

- `public static System.String unityExe { get }`  

```csharp
public static System.String unityExe { get; }
```

- `public static System.String unityUninstallerExe { get }`  

```csharp
public static System.String unityUninstallerExe { get; }
```

- `public System.String installerPath { get }`  

```csharp
public System.String installerPath { get; }
```

- `public System.String installationDirectory { get; set }`  

```csharp
public System.String installationDirectory { get; set; }
```

- `public System.Boolean canChangeInstallationDirectory { get }`  

```csharp
public System.Boolean canChangeInstallationDirectory { get; }
```

- `public System.Boolean confirmUninstallation { get }`  

```csharp
public System.Boolean confirmUninstallation { get; }
```

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```


## Constructors

- `public UnityDependency()`  

```csharp
public UnityDependency()
	{
		sUnityPath = null;
		installationDirectory = kDefaultInstallationDirectory;
	}
```


## Methods

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override Task Download(CancellationToken token)
	{
		return BaseDependency.Download(this, token, "https://download.unity3d.com/download_unity/7670c08855a9/Windows64EditorInstaller/UnitySetup64-2022.3.62f2.exe", installerPath, "DownloadingUnity");
	}
```

- `public virtual GetRequiredDiskSpace(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>>`  

```csharp
public override async Task<List<IToolchainDependency.DiskSpaceRequirements>> GetRequiredDiskSpace(CancellationToken token)
	{
		List<IToolchainDependency.DiskSpaceRequirements> requests = new List<IToolchainDependency.DiskSpaceRequirements>();
		if (!(await IsInstalled(token).ConfigureAwait(continueOnCapturedContext: false)))
		{
			requests.Add(new IToolchainDependency.DiskSpaceRequirements
			{
				m_Path = installationDirectory,
				m_Size = 6442450944L
			});
			if (await NeedDownload(token).ConfigureAwait(continueOnCapturedContext: false))
			{
				List<IToolchainDependency.DiskSpaceRequirements> list = requests;
				list.Add(new IToolchainDependency.DiskSpaceRequirements
				{
					m_Path = installerPath,
					m_Size = await GetUnityInstallerSize(token).ConfigureAwait(continueOnCapturedContext: false)
				});
			}
		}
		return requests;
	}
```

- `private GetUnityInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
private async Task<long> GetUnityInstallerSize(CancellationToken token)
	{
		m_DownloadSize.GetValueOrDefault();
		if (!m_DownloadSize.HasValue)
		{
			m_DownloadSize = await IToolchainDependency.GetDownloadSizeAsync("https://download.unity3d.com/download_unity/7670c08855a9/Windows64EditorInstaller/UnitySetup64-2022.3.62f2.exe", token).ConfigureAwait(continueOnCapturedContext: false);
		}
		return m_DownloadSize.Value;
	}
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Install(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		string path = installerPath;
		try
		{
			IToolchainDependency.log.Debug("Installing Unity");
			base.state = new IToolchainDependency.State(DependencyState.Installing, "InstallingUnity");
			await Cli.Wrap(path).WithArguments("/S").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				IToolchainDependency.log.Debug(l);
			}))
				.WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
				{
					IToolchainDependency.log.Error(l);
				}))
				.WithUseShellExecute(useShellExecute: true)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
		}
		catch (ToolchainException)
		{
			throw;
		}
		catch (OperationCanceledException)
		{
			throw;
		}
		catch (Exception innerException)
		{
			throw new ToolchainException(ToolchainError.Install, this, innerException);
		}
		finally
		{
			await AsyncUtils.DeleteFileAsync(path, token).ConfigureAwait(continueOnCapturedContext: false);
		}
	}
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> IsInstalled(CancellationToken token)
	{
		return Task.FromResult(unityExe != null && LongFile.Exists(unityExe));
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> IsUpToDate(CancellationToken token)
	{
		return IsInstalled(token);
	}
```

- `public virtual NeedDownload(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override async Task<bool> NeedDownload(CancellationToken token)
	{
		FileInfo installerFile = new FileInfo(installerPath);
		if (!installerFile.Exists)
		{
			return true;
		}
		long num = await GetUnityInstallerSize(token).ConfigureAwait(continueOnCapturedContext: false);
		if (installerFile.Length != num)
		{
			await AsyncUtils.DeleteFileAsync(installerPath, token).ConfigureAwait(continueOnCapturedContext: false);
			return true;
		}
		return false;
	}
```

- `private static TryGetParentPath(System.String path, System.Int32 depth, System.String& parentPath) : System.Boolean`  

```csharp
private static bool TryGetParentPath(string path, int depth, out string parentPath)
	{
		parentPath = null;
		if (string.IsNullOrEmpty(path))
		{
			return false;
		}
		DirectoryInfo directoryInfo = new DirectoryInfo(path);
		for (int i = 0; i < depth; i++)
		{
			directoryInfo = directoryInfo.Parent;
			if (directoryInfo == null)
			{
				return false;
			}
		}
		if (directoryInfo.Exists)
		{
			parentPath = directoryInfo.FullName;
			return true;
		}
		return false;
	}
```

- `private static TryGetRegistryKeyValue(Microsoft.Win32.RegistryKey registry, System.String path, System.String key, System.String& value) : System.Boolean`  

```csharp
private static bool TryGetRegistryKeyValue(RegistryKey registry, string path, string key, out string value)
	{
		value = null;
		RegistryKey registryKey = null;
		try
		{
			registryKey = registry.OpenSubKey(path);
			if (registryKey != null)
			{
				object value2 = registryKey.GetValue(key);
				if (value2 != null)
				{
					value = value2.ToString();
					return true;
				}
			}
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.Error(exception, "Failed checking registry key " + registry.Name + "\\" + path + key);
		}
		finally
		{
			registryKey?.Dispose();
		}
		return false;
	}
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Uninstall(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		try
		{
			IToolchainDependency.log.Debug("Uninstalling Unity");
			base.state = new IToolchainDependency.State(DependencyState.Removing, "RemovingUnity");
			string text = unityUninstallerExe;
			if (text != null)
			{
				await Cli.Wrap(text).WithArguments("/S /D=" + Path.Combine(installationDirectory, kInstallationFolder)).WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
				{
					IToolchainDependency.log.Debug(l);
				}))
					.WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
					{
						IToolchainDependency.log.Error(l);
					}))
					.WithUseShellExecute(useShellExecute: true)
					.ExecuteAsync(token)
					.ConfigureAwait(continueOnCapturedContext: false);
			}
			string unityPath = UnityDependency.unityPath;
			if (unityPath != null)
			{
				await AsyncUtils.WaitForAction(() => !LongDirectory.Exists(unityPath), token).ConfigureAwait(continueOnCapturedContext: false);
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

- `Game.Modding.Toolchain.Dependencies.UnityDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<>c__DisplayClass41_0`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<GetRequiredDiskSpace>d__38`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<GetUnityInstallerSize>d__37`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<Install>d__40`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<NeedDownload>d__36`  
- `Game.Modding.Toolchain.Dependencies.UnityDependency+<Uninstall>d__41`  

