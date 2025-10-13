# Game.Modding.Toolchain.Dependencies.BaseIDEDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class abstract public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public abstract class BaseIDEDependency : Game.Modding.Toolchain.Dependencies.BaseDependency, Game.Modding.Toolchain.IToolchainDependency
{
    public System.String minVersion { get; }
    public System.Boolean isMinVersion { get; }
    public System.String version { get; protected set; }

    protected BaseIDEDependency();

    private System.String <>n__0();
    private System.Threading.Tasks.Task<System.String> <get_version>b__5_0();
    protected abstract System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
    public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
    public System.Threading.Tasks.Task<System.String> GetVersion(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
    public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
}
```


## Properties

- `public System.String minVersion { get }`  

```csharp
public System.String minVersion { get; }
```

- `public System.Boolean isMinVersion { get }`  

```csharp
public System.Boolean isMinVersion { get; }
```

- `public System.String version { get; protected set }`  

```csharp
public System.String version { get; protected set; }
```


## Constructors

- `protected BaseIDEDependency()`  

```csharp
protected BaseIDEDependency();
```


## Methods

- `private <>n__0() : System.String`  

```csharp
private System.String <>n__0();
```

- `private <get_version>b__5_0() : System.Threading.Tasks.Task<System.String>`  

```csharp
private System.Threading.Tasks.Task<System.String> <get_version>b__5_0();
```

- `protected abstract GetIDEVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
protected abstract System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token);
```

- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public override LocalizedString GetLocalizedState(bool includeProgress)
	{
		return base.state.m_State switch
		{
			DependencyState.Installed => LocalizedString.Id("Options.STATE_TOOLCHAIN[Detected]"), 
			DependencyState.NotInstalled => LocalizedString.Id("Options.STATE_TOOLCHAIN[NotDetected]"), 
			DependencyState.Outdated => new LocalizedString("Options.STATE_TOOLCHAIN[DetectedOutdated]", null, new Dictionary<string, ILocElement> { 
			{
				"VERSION",
				LocalizedString.Value(version)
			} }), 
			_ => base.GetLocalizedState(includeProgress), 
		};
	}
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public override LocalizedString GetLocalizedVersion()
	{
		if (base.state.m_State == DependencyState.Installed)
		{
			return base.GetLocalizedVersion();
		}
		return new LocalizedString("Options.WARN_TOOLCHAIN_MIN_VERSION", null, new Dictionary<string, ILocElement> { 
		{
			"MIN_VERSION",
			LocalizedString.Value(minVersion)
		} });
	}
```

- `public GetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
public async Task<string> GetVersion(CancellationToken token)
	{
		string text = base.version;
		if (text == null)
		{
			text = await GetIDEVersion(token).ConfigureAwait(continueOnCapturedContext: false);
		}
		version = text;
		return version;
	}
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override async Task<bool> IsInstalled(CancellationToken token)
	{
		return !string.IsNullOrEmpty(await GetVersion(token).ConfigureAwait(continueOnCapturedContext: false));
	}
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public override async Task<bool> IsUpToDate(CancellationToken token)
	{
		if (System.Version.TryParse(await GetVersion(token).ConfigureAwait(continueOnCapturedContext: false), out var result) && System.Version.TryParse(minVersion, out var result2))
		{
			return result >= result2;
		}
		return false;
	}
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<<get_version>b__5_0>d`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<GetVersion>d__8`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<IsInstalled>d__9`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<IsUpToDate>d__10`  

