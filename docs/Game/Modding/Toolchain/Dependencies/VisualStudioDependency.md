# Game.Modding.Toolchain.Dependencies.VisualStudioDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseIDEDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class VisualStudioDependency : Game.Modding.Toolchain.Dependencies.BaseIDEDependency, Game.Modding.Toolchain.IToolchainDependency
{
    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }
    public static System.String vsWhere { get; }
    public System.String minVersion { get; }

    public VisualStudioDependency();

    protected virtual System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token);
    private static System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token, System.String arguments);
    private static System.Threading.Tasks.Task<Game.Modding.Toolchain.Dependencies.VsWhereResult> QueryVsWhere(System.Threading.CancellationToken token, System.String arguments);
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

- `public static System.String vsWhere { get }`  

```csharp
public static System.String vsWhere { get; }
```

- `public System.String minVersion { get }`  

```csharp
public System.String minVersion { get; }
```


## Constructors

- `public VisualStudioDependency()`  

```csharp
public VisualStudioDependency();
```


## Methods

- `protected virtual GetIDEVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
protected virtual System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token);
```

- `private static GetIDEVersion(System.Threading.CancellationToken token, System.String arguments) : System.Threading.Tasks.Task<System.String>`  

```csharp
private static System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token, System.String arguments);
```

- `private static QueryVsWhere(System.Threading.CancellationToken token, System.String arguments) : System.Threading.Tasks.Task<Game.Modding.Toolchain.Dependencies.VsWhereResult>`  

```csharp
private static System.Threading.Tasks.Task<Game.Modding.Toolchain.Dependencies.VsWhereResult> QueryVsWhere(System.Threading.CancellationToken token, System.String arguments);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.VisualStudioDependency+<>c__DisplayClass14_0`  
- `Game.Modding.Toolchain.Dependencies.VisualStudioDependency+<GetIDEVersion>d__13`  
- `Game.Modding.Toolchain.Dependencies.VisualStudioDependency+<QueryVsWhere>d__14`  

