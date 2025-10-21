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
public virtual Game.UI.Localization.LocalizedString GetLocalizedState(System.Boolean includeProgress);
```

- `public virtual GetLocalizedVersion() : Game.UI.Localization.LocalizedString`  

```csharp
public virtual Game.UI.Localization.LocalizedString GetLocalizedVersion();
```

- `public GetVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
public System.Threading.Tasks.Task<System.String> GetVersion(System.Threading.CancellationToken token);
```

- `public virtual IsInstalled(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsInstalled(System.Threading.CancellationToken token);
```

- `public virtual IsUpToDate(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.Boolean>`  

```csharp
public virtual System.Threading.Tasks.Task<System.Boolean> IsUpToDate(System.Threading.CancellationToken token);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<<get_version>b__5_0>d`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<GetVersion>d__8`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<IsInstalled>d__9`  
- `Game.Modding.Toolchain.Dependencies.BaseIDEDependency+<IsUpToDate>d__10`  

