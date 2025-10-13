# Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class ProjectTemplateDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private static readonly System.String kPropsFileSource;
    private static readonly System.String kTargetsFileSource;
    private static readonly System.String kPropsFileDeploy;
    private static readonly System.String kTargetsFileDeploy;
    private static readonly System.String kTemplatePackageFile;
    private static readonly System.String kTemplatePackageSource;
    private static readonly System.String kTemplatePackageInstallation;
    private static const System.String kProjectName;
    private static const System.String kPropsFile;
    private static const System.String kTargetsFile;
    private static const System.String kTemplatePackageId;
    private static const System.String kTemplateId;

    public System.String name { get; }
    public System.String icon { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Collections.Generic.IEnumerable<System.String> envVariables { get; }

    public ProjectTemplateDependency();

    internal static System.UInt64 <IsUpToDate>g__CalculateCache|25_0(System.String file);
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency+DiskSpaceRequirements>> GetRequiredDiskSpace(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private static readonly System.String kPropsFileSource`  

```csharp
private static readonly System.String kPropsFileSource;
```

- `private static readonly System.String kTargetsFileSource`  

```csharp
private static readonly System.String kTargetsFileSource;
```

- `private static readonly System.String kPropsFileDeploy`  

```csharp
private static readonly System.String kPropsFileDeploy;
```

- `private static readonly System.String kTargetsFileDeploy`  

```csharp
private static readonly System.String kTargetsFileDeploy;
```

- `private static readonly System.String kTemplatePackageFile`  

```csharp
private static readonly System.String kTemplatePackageFile;
```

- `private static readonly System.String kTemplatePackageSource`  

```csharp
private static readonly System.String kTemplatePackageSource;
```

- `private static readonly System.String kTemplatePackageInstallation`  

```csharp
private static readonly System.String kTemplatePackageInstallation;
```

- `private static const System.String kProjectName`  

```csharp
private static const System.String kProjectName;
```

- `private static const System.String kPropsFile`  

```csharp
private static const System.String kPropsFile;
```

- `private static const System.String kTargetsFile`  

```csharp
private static const System.String kTargetsFile;
```

- `private static const System.String kTemplatePackageId`  

```csharp
private static const System.String kTemplatePackageId;
```

- `private static const System.String kTemplateId`  

```csharp
private static const System.String kTemplateId;
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

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

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


## Constructors

- `public ProjectTemplateDependency()`  

```csharp
public ProjectTemplateDependency();
```


## Methods

- `internal static <IsUpToDate>g__CalculateCache|25_0(System.String file) : System.UInt64`  

```csharp
internal static System.UInt64 <IsUpToDate>g__CalculateCache|25_0(System.String file);
```

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
				m_Path = kPropsFileDeploy,
				m_Size = new FileInfo(kPropsFileSource).Length
			},
			new IToolchainDependency.DiskSpaceRequirements
			{
				m_Path = kTargetsFileDeploy,
				m_Size = new FileInfo(kTargetsFileSource).Length
			},
			new IToolchainDependency.DiskSpaceRequirements
			{
				m_Path = kTemplatePackageInstallation,
				m_Size = new FileInfo(kTemplatePackageSource).Length
			}
		});
	}
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Install(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		try
		{
			IToolchainDependency.log.DebugFormat("Installing {0}", "C# Mod project template");
			base.state = new IToolchainDependency.State(DependencyState.Installing, "InstallingModTemplate");
			IToolchainDependency.log.DebugFormat("Copy mod template properties file '{0}' to '{1}'", kPropsFileSource, kPropsFileDeploy);
			IOUtils.EnsureDirectory(Path.GetDirectoryName(kPropsFileDeploy));
			await AsyncUtils.CopyFileAsync(kPropsFileSource, kPropsFileDeploy, overwrite: true, token).ConfigureAwait(continueOnCapturedContext: false);
			IToolchainDependency.log.DebugFormat("Copy mod template targets file '{0}' to '{1}'", kTargetsFileSource, kTargetsFileDeploy);
			IOUtils.EnsureDirectory(Path.GetDirectoryName(kTargetsFileDeploy));
			await AsyncUtils.CopyFileAsync(kTargetsFileSource, kTargetsFileDeploy, overwrite: true, token).ConfigureAwait(continueOnCapturedContext: false);
			IToolchainDependency.log.DebugFormat("Install mod template package '{0}'", kTemplatePackageSource);
			System.Version dotnetVersion = await DotNetDependency.GetDotnetVersion(token).ConfigureAwait(continueOnCapturedContext: false);
			if (dotnetVersion.Major < 6)
			{
				throw new ToolchainException(ToolchainError.Install, this, ".net6.0 is required");
			}
			List<string> errorText = new List<string>();
			await Cli.Wrap("dotnet").WithArguments((dotnetVersion.Major == 6) ? "new --uninstall ColossalOrder.ModTemplate" : "new uninstall ColossalOrder.ModTemplate --verbosity q").WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				errorText.Add(l);
			}))
				.WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
			errorText.Clear();
			CommandResult obj = await Cli.Wrap("dotnet").WithArguments((dotnetVersion.Major == 6) ? ("new --install \"" + kTemplatePackageSource + "\" --force") : ("new install \"" + kTemplatePackageSource + "\" --force --verbosity q")).WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				errorText.Add(l);
			}))
				.WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
			if (obj.ExitCode != 0)
			{
				throw new ToolchainException(ToolchainError.Install, this, "Mod template package not installed: code {result.ExitCode}");
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
		_ = 1;
		try
		{
			if (!LongFile.Exists(kPropsFileDeploy) || !LongFile.Exists(kTargetsFileDeploy))
			{
				return false;
			}
			System.Version version = await DotNetDependency.GetDotnetVersion(token).ConfigureAwait(continueOnCapturedContext: false);
			if (version.Major < 6)
			{
				return false;
			}
			List<string> errorText = new List<string>();
			CommandResult obj = await Cli.Wrap("dotnet").WithArguments((version.Major == 6) ? "new --list csiimod" : "new list csiimod --verbosity q").WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				errorText.Add(l);
			}))
				.WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
			if (obj.ExitCode != 0)
			{
				return false;
			}
			return true;
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.Error(exception, "Error during mod template check");
			return false;
		}
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> IsUpToDate(CancellationToken token)
	{
		try
		{
			if (CalculateCache(kPropsFileSource) != CalculateCache(kPropsFileDeploy))
			{
				return Task.FromResult(result: false);
			}
			if (CalculateCache(kTargetsFileSource) != CalculateCache(kTargetsFileDeploy))
			{
				return Task.FromResult(result: false);
			}
			if (CalculateCache(kTemplatePackageSource) != CalculateCache(kTemplatePackageInstallation))
			{
				return Task.FromResult(result: false);
			}
			return Task.FromResult(result: true);
		}
		catch (Exception exception)
		{
			IToolchainDependency.log.Error(exception, "Error during mod template check");
			return Task.FromResult(result: false);
		}
		static ulong CalculateCache(string file)
		{
			if (!LongFile.Exists(file))
			{
				return 0uL;
			}
			byte[] data = LongFile.ReadAllBytes(file);
			return new Crc(new CrcParameters(64, 4823603603198064275uL, 0uL, 0uL, reflectIn: false, reflectOut: false)).CalculateAsNumeric(data);
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

- `public virtual Uninstall(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Uninstall(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		try
		{
			base.state = new IToolchainDependency.State(DependencyState.Removing, "RemovingProjectTemplate");
			IToolchainDependency.log.DebugFormat("Removing {0}", "C# Mod project template");
			await AsyncUtils.DeleteFileAsync(kPropsFileDeploy, token).ConfigureAwait(continueOnCapturedContext: false);
			await AsyncUtils.DeleteFileAsync(kTargetsFileDeploy, token).ConfigureAwait(continueOnCapturedContext: false);
			System.Version version = await DotNetDependency.GetDotnetVersion(token).ConfigureAwait(continueOnCapturedContext: false);
			if (version.Major < 6)
			{
				throw new ToolchainException(ToolchainError.Uninstall, this, ".net6.0 is required");
			}
			List<string> errorText = new List<string>();
			CommandResult obj = await Cli.Wrap("dotnet").WithArguments((version.Major == 6) ? "new --uninstall ColossalOrder.ModTemplate" : "new uninstall ColossalOrder.ModTemplate").WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				errorText.Add(l);
			}))
				.WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token)
				.ConfigureAwait(continueOnCapturedContext: false);
			if (errorText.Count > 0)
			{
				IToolchainDependency.log.Warn(string.Join('\n', errorText));
			}
			if (obj.ExitCode != 0)
			{
				throw new ToolchainException(ToolchainError.Uninstall, this, "Mod template package not removed: code {result.ExitCode}");
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

- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass24_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass28_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<>c__DisplayClass29_0`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<Install>d__28`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<IsInstalled>d__24`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<Uninstall>d__29`  
- `Game.Modding.Toolchain.Dependencies.ProjectTemplateDependency+<get_envVariables>d__23`  

