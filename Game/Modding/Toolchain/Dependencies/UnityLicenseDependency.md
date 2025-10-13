# Game.Modding.Toolchain.Dependencies.UnityLicenseDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class UnityLicenseDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private static readonly System.String kSerialBasedLicenseFile;
    private static readonly System.String kNamedUserLicenseFile;

    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean confirmUninstallation { get; }
    public Game.UI.Localization.LocalizedString installDescr { get; }
    public Game.UI.Localization.LocalizedString uninstallMessage { get; }
    public System.Type[] dependsOnInstallation { get; }
    public System.Type[] dependsOnUninstallation { get; }
    public System.Boolean licenseExists { get; }

    public UnityLicenseDependency();

    private System.Boolean <Install>b__22_0();
    public virtual System.Threading.Tasks.Task Download(System.Threading.CancellationToken token);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public virtual System.Threading.Tasks.Task Install(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> NeedDownload(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task Uninstall(System.Threading.CancellationToken token);
}
```


## Fields

- `private static readonly System.String kSerialBasedLicenseFile`  

```csharp
private static readonly System.String kSerialBasedLicenseFile;
```

- `private static readonly System.String kNamedUserLicenseFile`  

```csharp
private static readonly System.String kNamedUserLicenseFile;
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

- `public Game.UI.Localization.LocalizedString installDescr { get }`  

```csharp
public Game.UI.Localization.LocalizedString installDescr { get; }
```

- `public Game.UI.Localization.LocalizedString uninstallMessage { get }`  

```csharp
public Game.UI.Localization.LocalizedString uninstallMessage { get; }
```

- `public System.Type[] dependsOnInstallation { get }`  

```csharp
public System.Type[] dependsOnInstallation { get; }
```

- `public System.Type[] dependsOnUninstallation { get }`  

```csharp
public System.Type[] dependsOnUninstallation { get; }
```

- `public System.Boolean licenseExists { get }`  

```csharp
public System.Boolean licenseExists { get; }
```


## Constructors

- `public UnityLicenseDependency()`  

```csharp
public UnityLicenseDependency();
```


## Methods

- `private <Install>b__22_0() : System.Boolean`  

```csharp
private System.Boolean <Install>b__22_0();
```

- `public virtual Download(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override Task Download(CancellationToken token)
	{
		return Task.CompletedTask;
	}
```

- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public override LocalizedString GetLocalizedState(bool includeProgress)
	{
		return base.state.m_State switch
		{
			DependencyState.Installed => LocalizedString.Id("Options.STATE_TOOLCHAIN[Activated]"), 
			DependencyState.Installing => LocalizedString.Id("Options.STATE_TOOLCHAIN[WaitingForActivation]"), 
			DependencyState.NotInstalled => LocalizedString.Id("Options.STATE_TOOLCHAIN[NotActivated]"), 
			DependencyState.Removing => LocalizedString.Id("Options.STATE_TOOLCHAIN[Returning]"), 
			_ => IToolchainDependency.GetLocalizedState(base.state, includeProgress), 
		};
	}
```

- `public virtual Install(System.Threading.CancellationToken token) : System.Threading.Tasks.Task`  

```csharp
public override async Task Install(CancellationToken token)
	{
		token.ThrowIfCancellationRequested();
		try
		{
			IToolchainDependency.log.Debug("Waiting for Unity license");
			base.state = new IToolchainDependency.State(DependencyState.Installing, "WaitingUnityLicense");
			Cli.Wrap(UnityDependency.unityExe).WithArguments(new string[3]
			{
				"-projectPath",
				UnityModProjectDependency.kProjectUnzipPath,
				"-quit"
			}).WithValidation(CommandResultValidation.None)
				.ExecuteAsync(token);
			await AsyncUtils.WaitForAction(() => licenseExists, token).ConfigureAwait(continueOnCapturedContext: false);
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
		return Task.FromResult(licenseExists);
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override Task<bool> IsUpToDate(CancellationToken token)
	{
		return Task.FromResult(result: true);
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
			if (LongFile.Exists(kSerialBasedLicenseFile))
			{
				IToolchainDependency.log.Debug("Return Unity license");
				base.state = new IToolchainDependency.State(DependencyState.Removing, "ReturningUnityLicense");
				await Cli.Wrap(UnityDependency.unityExe).WithArguments(new string[2] { "-returnlicense", "-quit" }).WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
				{
					IToolchainDependency.log.Debug(l);
				}))
					.WithStandardErrorPipe(PipeTarget.ToDelegate(delegate(string l)
					{
						IToolchainDependency.log.Error(l);
					}))
					.ExecuteAsync(token)
					.ConfigureAwait(continueOnCapturedContext: false);
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

- `Game.Modding.Toolchain.Dependencies.UnityLicenseDependency+<>c`  
- `Game.Modding.Toolchain.Dependencies.UnityLicenseDependency+<Install>d__22`  
- `Game.Modding.Toolchain.Dependencies.UnityLicenseDependency+<Uninstall>d__23`  

