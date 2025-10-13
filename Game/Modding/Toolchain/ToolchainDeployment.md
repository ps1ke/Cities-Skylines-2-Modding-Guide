# Game.Modding.Toolchain.ToolchainDeployment

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ToolchainDeployment
{
    private static readonly Game.Modding.Toolchain.ToolchainDependencyManager <dependencyManager>k__BackingField;

    public static Game.Modding.Toolchain.ToolchainDependencyManager dependencyManager { get; }

    public static System.Threading.Tasks.Task Run(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies);
    private static System.Threading.Tasks.Task RunImpl(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies);
    public static System.Void RunWithUI(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies, System.Action<System.Boolean> callback);
}
```


## Fields

- `private static readonly Game.Modding.Toolchain.ToolchainDependencyManager <dependencyManager>k__BackingField`  

```csharp
private static readonly Game.Modding.Toolchain.ToolchainDependencyManager <dependencyManager>k__BackingField;
```


## Properties

- `public static Game.Modding.Toolchain.ToolchainDependencyManager dependencyManager { get }`  

```csharp
public static Game.Modding.Toolchain.ToolchainDependencyManager dependencyManager { get; }
```


## Methods

- `public static Run(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies = null) : System.Threading.Tasks.Task`  

```csharp
public static async Task Run(DeploymentAction action, List<IToolchainDependency> dependencies = null)
	{
		if (!dependencyManager.isInProgress)
		{
			(List<IToolchainDependency>, List<IToolchainDependency>) tuple = ToolchainDependencyManager.DependencyFilter.Process(action, dependencies);
			if (tuple.Item1.Count != 0)
			{
				await RunImpl(action, tuple.Item1);
			}
		}
	}
```

- `private static RunImpl(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies) : System.Threading.Tasks.Task`  

```csharp
private static async Task RunImpl(DeploymentAction action, List<IToolchainDependency> dependencies)
	{
		if (action < DeploymentAction.Uninstall)
		{
			await TaskManager.instance.SharedTask("InstallToolchain", dependencyManager.Install, dependencies, GameManager.instance.terminationToken);
		}
		else
		{
			await TaskManager.instance.SharedTask("UninstallToolchain", dependencyManager.Uninstall, dependencies, GameManager.instance.terminationToken);
		}
	}
```

- `public static RunWithUI(Game.Modding.Toolchain.DeploymentAction action, System.Collections.Generic.List<Game.Modding.Toolchain.IToolchainDependency> dependencies = null, System.Action<System.Boolean> callback = null) : System.Void`  

```csharp
public static async void RunWithUI(DeploymentAction action, List<IToolchainDependency> dependencies = null, Action<bool> callback = null)
	{
		if (dependencyManager.isInProgress)
		{
			return;
		}
		(List<IToolchainDependency> accepted, List<IToolchainDependency> discarded) filtered = ToolchainDependencyManager.DependencyFilter.Process(action, dependencies);
		if (filtered.accepted.Count == 0)
		{
			callback?.Invoke(dependencies == null);
			await dependencyManager.GetCurrentState();
			return;
		}
		filtered.accepted.Sort((action < DeploymentAction.Uninstall) ? new Comparison<IToolchainDependency>(IToolchainDependency.InstallSorting) : new Comparison<IToolchainDependency>(IToolchainDependency.UninstallSorting));
		TaskCompletionSource<bool> tcs = new TaskCompletionSource<bool>();
		Dictionary<string, ILocElement> dictionary = new Dictionary<string, ILocElement>();
		foreach (IToolchainDependency item in filtered.accepted)
		{
			dictionary.Add($"Item{dictionary.Count}", (action < DeploymentAction.Uninstall) ? item.installDescr : item.uninstallDescr);
		}
		LocalizedString message = LocalizedString.Id((action < DeploymentAction.Uninstall) ? "Options.WARN_TOOLCHAIN_INSTALL_NEW" : "Options.WARN_TOOLCHAIN_UNINSTALL_NEW");
		ConfirmationDialog dialog = new ConfirmationDialog(details: new LocalizedString(null, string.Join("\n\n", dictionary.Keys.Select((string key) => "- {" + key + "}")), dictionary), title: "Common.DIALOG_TITLE[Warning]", message: message, copyButton: false, confirmAction: "Common.DIALOG_ACTION[Yes]", cancelAction: "Common.DIALOG_ACTION[No]", otherActions: Array.Empty<LocalizedString>());
		GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(dialog, delegate(int msg)
		{
			tcs.SetResult(msg == 0);
		});
		bool goAhead = await tcs.Task;
		if (goAhead)
		{
			await RunImpl(action, filtered.accepted);
		}
		callback?.Invoke(goAhead);
	}
```


## Nested types

- `Game.Modding.Toolchain.ToolchainDeployment+<>c`  
- `Game.Modding.Toolchain.ToolchainDeployment+<>c__DisplayClass4_0`  
- `Game.Modding.Toolchain.ToolchainDeployment+<Run>d__5`  
- `Game.Modding.Toolchain.ToolchainDeployment+<RunImpl>d__6`  
- `Game.Modding.Toolchain.ToolchainDeployment+<RunWithUI>d__4`  

