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
public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.IDEDependency+<>c`  

