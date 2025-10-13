# Game.Modding.Toolchain.Dependencies.VSCodeDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseIDEDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class VSCodeDependency : Game.Modding.Toolchain.Dependencies.BaseIDEDependency, Game.Modding.Toolchain.IToolchainDependency
{
    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }
    public System.String minVersion { get; }

    public VSCodeDependency();

    protected virtual System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token);
}
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

- `public System.Boolean canBeInstalled { get }`  

```csharp
public System.Boolean canBeInstalled { get; }
```

- `public System.Boolean canBeUninstalled { get }`  

```csharp
public System.Boolean canBeUninstalled { get; }
```

- `public System.String minVersion { get }`  

```csharp
public System.String minVersion { get; }
```


## Constructors

- `public VSCodeDependency()`  

```csharp
public VSCodeDependency();
```


## Methods

- `protected virtual GetIDEVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
protected override async Task<string> GetIDEVersion(CancellationToken token)
	{
		string installedVersion = string.Empty;
		List<string> errorText = new List<string>();
		try
		{
			await Cli.Wrap("code").WithArguments("--version").WithStandardOutputPipe(PipeTarget.ToDelegate(delegate(string l)
			{
				if (string.IsNullOrEmpty(installedVersion))
				{
					installedVersion = l;
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
				ToolchainDependencyManager.log.Error(ex, "Failed to get VSCode version");
			}
		}
		catch (Exception exception)
		{
			ToolchainDependencyManager.log.Error(exception, "Failed to get VSCode version");
		}
		if (errorText.Count > 0)
		{
			IToolchainDependency.log.Warn(string.Join('\n', errorText));
		}
		return installedVersion;
	}
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.VSCodeDependency+<>c__DisplayClass10_0`  
- `Game.Modding.Toolchain.Dependencies.VSCodeDependency+<GetIDEVersion>d__10`  

