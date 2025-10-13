# Game.Modding.Toolchain.Dependencies.DotNetDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class DotNetDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private System.Nullable<System.Int64> m_DownloadSize;
    private System.String m_InstallationDirectory;
    private static readonly System.String sDotNetVersion;
    public static readonly System.String sDotNetInstallerUrl;
    public static readonly System.String kDefaultInstallationDirectory;
    public static readonly System.String kInstallationFolder;
    private static const System.String kDependencyName;

    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean confirmUninstallation { get; }
    public System.String installerPath { get; }
    public System.String installationDirectory { get; set; }
    public System.Boolean canChangeInstallationDirectory { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.String version { get; protected set; }

    public DotNetDependency();

    private System.Void <>n__0(System.String value);
    private System.String <>n__1();
    private System.Threading.Tasks.Task<System.String> <get_version>b__33_0();
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.Int64> GetDotNetInstallerSize(System.Threading.CancellationToken token);
    public static System.Threading.Tasks.Task<System.Version> GetDotnetVersion(System.Threading.CancellationToken token);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    private System.Threading.Tasks.Task<System.String> GetVersion(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
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

- `private static readonly System.String sDotNetVersion`  

```csharp
private static readonly System.String sDotNetVersion;
```

- `public static readonly System.String sDotNetInstallerUrl`  

```csharp
public static readonly System.String sDotNetInstallerUrl;
```

- `public static readonly System.String kDefaultInstallationDirectory`  

```csharp
public static readonly System.String kDefaultInstallationDirectory;
```

- `public static readonly System.String kInstallationFolder`  

```csharp
public static readonly System.String kInstallationFolder;
```

- `private static const System.String kDependencyName`  

```csharp
private static const System.String kDependencyName;
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

- `public DotNetDependency()`  

```csharp
public DotNetDependency()
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

- `private <get_version>b__33_0() : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> <get_version>b__33_0();
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override Task Download(CancellationToken token)
	{
		return BaseDependency.Download(this, token, sDotNetInstallerUrl, installerPath, "DownloadingDotNet");
	}
```

- `private GetDotNetInstallerSize(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Int64>`  

```csharp
private async Task<long> GetDotNetInstallerSize(CancellationToken token)
	{
		m_DownloadSize.GetValueOrDefault();
		if (!m_DownloadSize.HasValue)
		{
			m_DownloadSize = await IToolchainDependency.GetDownloadSizeAsync(sDotNetInstallerUrl, token).ConfigureAwait(continueOnCapturedContext: false);
		}
		return m_DownloadSize.Value;
	}
```

- `public static GetDotnetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Version>`  

```csharp
public static async Task<System.Version> GetDotnetVersion(CancellationToken token)
	{
		System.Version installedVersion = new System.Version();
		List<string> errorText = new List<string>();
		try
		{
			await Cli.Wrap("dotnet").WithArguments("--version").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				if (System.Version.TryParse(l, out var result))
				{
					installedVersion = result;
				}
				else
				{
					int num = l.IndexOf('-');
					if (num > 0 && System.Version.TryParse(l.Substring(0, num), out result))
					{
						installedVersion = result;
					}
					else
					{
						IToolchainDependency.log.ErrorFormat("Failed to parse {0} version number \"{1}\"", ".Net", l);
					}
				}
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
				IToolchainDependency.log.ErrorFormat(ex, "Failed to get {0} version", ".Net");
			}
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.ErrorFormat(exception, "Failed to get {0} version", ".Net");
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
		}
		return installedVersion;
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
				LocalizedString.Value("6.0")
			} });
		}
		return base.GetLocalizedVersion();
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
				m_Size = 1073741824L
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

- `private GetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
private async Task<string> GetVersion(CancellationToken token)
	{
		System.Version version = await GetDotnetVersion(token).ConfigureAwait(continueOnCapturedContext: false);
		base.version = ((version.Major != 0) ? version.ToString() : string.Empty);
		return base.version;
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
			IToolchainDependency.log.DebugFormat("Installing {0}", ".Net");
			base.state = new IToolchainDependency.State(DependencyState.Installing, "InstallingDotNet");
			await Cli.Wrap(path).WithArguments("/install /quiet /norestart INSTALLDIR=\"" + Path.Combine(installationDirectory, kInstallationFolder) + "\" ").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
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
		return (await GetDotnetVersion(token).ConfigureAwait(continueOnCapturedContext: false)).Major >= 6;
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
			IToolchainDependency.log.DebugFormat("Uninstalling {0}", ".Net");
			base.state = new IToolchainDependency.State(DependencyState.Removing, "RemovingDotNet");
			Dictionary<string, string> dictionary = new Dictionary<string, string>();
			dictionary.Add("DisplayName", "Microsoft .NET SDK " + version + " (" + RuntimeInformation.OSArchitecture.ToString().ToLower() + ")");
			if (IToolchainDependency.GetUninstaller(dictionary, out var keyName) == null)
			{
				throw new ToolchainException(ToolchainError.Uninstall, this, "Uninstaller not found");
			}
			await Cli.Wrap(Path.Combine(Environment.GetFolderPath(Environment.SpecialFolder.CommonApplicationData), "Package Cache", keyName, "dotnet-sdk-" + version + "-win-" + RuntimeInformation.OSArchitecture.ToString().ToLower() + ".exe")).WithArguments("/uninstall /quiet").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
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

- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<<get_version>b__33_0>d`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<>c__DisplayClass37_0`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetDotNetInstallerSize>d__27`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetDotnetVersion>d__37`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetRequiredDiskSpace>d__28`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<GetVersion>d__35`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<Install>d__30`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<IsInstalled>d__25`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<NeedDownload>d__26`  
- `Game.Modding.Toolchain.Dependencies.DotNetDependency+<Uninstall>d__31`  

