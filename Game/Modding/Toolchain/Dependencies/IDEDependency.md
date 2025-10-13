# Game.Modding.Toolchain.Dependencies.IDEDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.CombinedDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class IDEDependency : Game.Modding.Toolchain.Dependencies.CombinedDependency, Game.Modding.Toolchain.IToolchainDependency
{
    private Game.Modding.Toolchain.Dependencies.BaseIDEDependency[] ides;

    public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
    public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get; }
    protected System.Boolean isAsync { protected get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }

    public IDEDependency();

    public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
}
```


## Fields

- `private Game.Modding.Toolchain.Dependencies.BaseIDEDependency[] ides`  

```csharp
private Game.Modding.Toolchain.Dependencies.BaseIDEDependency[] ides;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Modding.Toolchain.IToolchainDependency> dependencies { get; }
```

- `public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get }`  

```csharp
public Game.Modding.Toolchain.Dependencies.CombinedDependency+CombineType type { get; }
```

- `protected System.Boolean isAsync { protected get }`  

```csharp
protected System.Boolean isAsync { protected get; }
```

- `public System.Boolean canBeInstalled { get }`  

```csharp
public System.Boolean canBeInstalled { get; }
```

- `public System.Boolean canBeUninstalled { get }`  

```csharp
public System.Boolean canBeUninstalled { get; }
```


## Constructors

- `public IDEDependency()`  

```csharp
public IDEDependency();
```


## Methods

- `public virtual GetLocalizedState(System.Boolean includeProgress) : Game.UI.Localization.LocalizedString`  

```csharp
public override LocalizedString GetLocalizedState(bool includeProgress)
	{
		switch (base.state.m_State)
		{
		case DependencyState.Installed:
		{
			Dictionary<string, ILocElement> dictionary = new Dictionary<string, ILocElement> { 
			{
				"STATE",
				LocalizedString.Id("Options.STATE_TOOLCHAIN[Detected]")
			} };
			BaseIDEDependency[] array = ides;
			foreach (BaseIDEDependency baseIDEDependency in array)
			{
				if (baseIDEDependency.isMinVersion)
				{
					dictionary.Add($"Item{dictionary.Count}", new LocalizedString(null, "{NAME}", new Dictionary<string, ILocElement> { { "NAME", baseIDEDependency.localizedName } }));
				}
			}
			return new LocalizedString(null, "{STATE} (" + string.Join(", ", from k in dictionary.Keys.Skip(1)
				select "{" + k + "}") + ")", dictionary);
		}
		case DependencyState.NotInstalled:
			return LocalizedString.Id("Options.STATE_TOOLCHAIN[NotDetected]");
		default:
			return base.GetLocalizedState(includeProgress);
		}
	}
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.IDEDependency+<>c`  

