# Game.Modding.Toolchain.Dependencies.NodeJSDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class NodeJSDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private System.Nullable<System.Int64> m_DownloadSize;
    private System.String m_InstallationDirectory;
    public static readonly System.String kNodeJSVersion;
    public static readonly System.String kMinNodeJSVersion;
    public static readonly System.String kNodeJSInstallerUrl;
    public static readonly System.String kDefaultInstallationDirectory;
    public static readonly System.String kInstallationFolder;

    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean confirmUninstallation { get; }
    public System.String installerPath { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.String version { get; protected set; }

    public NodeJSDependency();

    private System.Void <>n__0(System.String value);
    private System.String <>n__1();
    private System.Threading.Tasks.Task<System.String> <get_version>b__34_0();
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Int64> GetDotNetInstallerSize(System.Threading.CancellationToken token);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    private System.Threading.Tasks.Task<System.String> GetNodeVersion(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
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

- `public static readonly System.String kNodeJSVersion`  

```csharp
public static readonly System.String kNodeJSVersion;
```

- `public static readonly System.String kMinNodeJSVersion`  

```csharp
public static readonly System.String kMinNodeJSVersion;
```

- `public static readonly System.String kNodeJSInstallerUrl`  

```csharp
public static readonly System.String kNodeJSInstallerUrl;
```

- `public static readonly System.String kDefaultInstallationDirectory`  

```csharp
public static readonly System.String kDefaultInstallationDirectory;
```

- `public static readonly System.String kInstallationFolder`  

```csharp
public static readonly System.String kInstallationFolder;
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

- `public System.Boolean confirmUninstallation { get }`  

```csharp
public System.Boolean confirmUninstallation { get; }
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

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```


## Constructors

- `public NodeJSDependency()`  

```csharp
public NodeJSDependency()
	{
		installationDirectory = kDefaultInstallationDirectory;
	}
```


## Methods

- `private <>n__0(System.String value) : System.Void`  

```csharp
private System.Void <>n__0(System.String value);
```

- `private <>n__1() : System.String`  

```csharp
private System.String <>n__1();
```

- `private <get_version>b__34_0() : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> <get_version>b__34_0();
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override Task Download(CancellationToken token)
	{
		return BaseDependency.Download(this, token, kNodeJSInstallerUrl, installerPath, "DownloadingNodeJS");
	}
```

- `private GetDotNetInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
private async Task<long> GetDotNetInstallerSize(CancellationToken token)
	{
		m_DownloadSize.GetValueOrDefault();
		if (!m_DownloadSize.HasValue)
		{
			m_DownloadSize = await IToolchainDependency.GetDownloadSizeAsync(kNodeJSInstallerUrl, token).ConfigureAwait(continueOnCapturedContext: false);
		}
		return m_DownloadSize.Value;
	}
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public override LocalizedString GetLocalizedVersion()
	{
		if (string.IsNullOrEmpty(version))
		{
			return new LocalizedString("Options.WARN_TOOLCHAIN_MIN_VERSION", null, new Dictionary<string, ILocElement> { 
			{
				"MIN_VERSION",
				LocalizedString.Value(kMinNodeJSVersion)
			} });
		}
		return base.GetLocalizedVersion();
	}
```

- `private GetNodeVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
private async Task<string> GetNodeVersion(CancellationToken token)
	{
		string installedVersion = string.Empty;
		List<string> errorText = new List<string>();
		try
		{
			await Cli.Wrap("node").WithArguments("-v").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				installedVersion = l;
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
				IToolchainDependency.log.ErrorFormat(ex, "Failed to get {0} version", name);
			}
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.ErrorFormat(exception, "Failed to get {0} version", name);
		}
		if (errorText.Count > 0)
		{
			IToolchainDependency.log.Warn(string.Join('\n', errorText));
		}
		NodeJSDependency nodeJSDependency = this;
		string text;
		if (!installedVersion.StartsWith('v'))
		{
			text = installedVersion;
		}
		else
		{
			string text2 = installedVersion;
			text = text2.Substring(1, text2.Length - 1);
		}
		((BaseDependency)nodeJSDependency).version = text;
		return base.version;
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
				m_Size = 104857600L
			});
			if (await NeedDownload(token).ConfigureAwait(continueOnCapturedContext: false))
			{
				List<IToolchainDependency.DiskSpaceRequirements> list = requests;
				list.Add(new IToolchainDependency.DiskSpaceRequirements
				{
					m_Path = installerPath,
					m_Size = await GetDotNetInstallerSize(token).ConfigureAwait(continueOnCapturedContext: false)
				});
			}
		}
		return requests;
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
			IToolchainDependency.log.DebugFormat("Installing {0}", name);
			base.state = new IToolchainDependency.State(DependencyState.Installing, "InstallingNodeJS");
			await Cli.Wrap("msiexec").WithArguments("/i \"" + path + "\" /passive /norestart INSTALLDIR=\"" + installationDirectory + "\" ").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
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
			IToolchainDependency.UpdateProcessEnvVarPathValue();
		}
		catch (ToolchainException)
		{
			throw;
		}
		catch (OperationCanceledException)
		{
			throw;
		}
		catch (CommandExecutionException ex3)
		{
			if (ex3.ExitCode == 1602 || ex3.ExitCode == 1603)
			{
				throw new ToolchainException(ToolchainError.Install, this, "Installation canceled by user");
			}
			throw new ToolchainException(ToolchainError.Install, this, ex3);
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
public override async Task<bool> IsInstalled(CancellationToken token)
	{
		return !string.IsNullOrEmpty(await GetNodeVersion(token).ConfigureAwait(continueOnCapturedContext: false));
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override async Task<bool> IsUpToDate(CancellationToken token)
	{
		string input = await GetNodeVersion(token).ConfigureAwait(continueOnCapturedContext: false);
		if (System.Version.TryParse(kMinNodeJSVersion, out var result) && System.Version.TryParse(input, out var result2))
		{
			return result2 >= result;
		}
		return false;
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
		long num = await GetDotNetInstallerSize(token).ConfigureAwait(continueOnCapturedContext: false);
		if (installerFile.Length != num)
		{
			await AsyncUtils.DeleteFileAsync(installerPath, token).ConfigureAwait(continueOnCapturedContext: false);
			return true;
		}
		return false;
	}
```

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Uninstall(CancellationToken token)
	{
		try
		{
			IToolchainDependency.log.DebugFormat("Uninstalling {0}", name);
			base.state = new IToolchainDependency.State(DependencyState.Removing, "RemovingNodeJS");
			if (IToolchainDependency.GetUninstaller(new Dictionary<string, string>
			{
				{ "DisplayName", "Node.js" },
				{ "DisplayVersion", version }
			}, out var keyName) == null)
			{
				throw new ToolchainException(ToolchainError.Uninstall, this, "Uninstaller not found");
			}
			await Cli.Wrap("msiexec").WithArguments("/x " + keyName + " /passive /norestart").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
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
		catch (CommandExecutionException ex3)
		{
			if (ex3.ExitCode == 1602 || ex3.ExitCode == 1603)
			{
				throw new ToolchainException(ToolchainError.Install, this, "Uninstallation canceled by user");
			}
			throw new ToolchainException(ToolchainError.Install, this, ex3);
		}
		catch (Exception innerException)
		{
			throw new ToolchainException(ToolchainError.Uninstall, this, innerException);
		}
	}
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<<get_version>b__34_0>d`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<>c__DisplayClass36_0`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<GetDotNetInstallerSize>d__28`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<GetNodeVersion>d__36`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<GetRequiredDiskSpace>d__29`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<Install>d__31`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<IsInstalled>d__25`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<IsUpToDate>d__26`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<NeedDownload>d__27`  
- `Game.Modding.Toolchain.Dependencies.NodeJSDependency+<Uninstall>d__32`  

