# Game.Modding.Toolchain.Dependencies.RiderDependency

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain.Dependencies`  

**Type:** class public  

**Base:** `Game.Modding.Toolchain.Dependencies.BaseIDEDependency`  
**Implements:** `Game.Modding.Toolchain.IToolchainDependency`  

## Code

```csharp
public class RiderDependency : Game.Modding.Toolchain.Dependencies.BaseIDEDependency, Game.Modding.Toolchain.IToolchainDependency
{
    public System.String name { get; }
    public System.String icon { get; }
    public System.Boolean canBeInstalled { get; }
    public System.Boolean canBeUninstalled { get; }
    public System.String minVersion { get; }

    public RiderDependency();

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

- `public RiderDependency()`  

```csharp
public RiderDependency();
```


## Methods

- `protected virtual GetIDEVersion(System.Threading.CancellationToken token) : System.Threading.Tasks.Task<System.String>`  

```csharp
protected virtual System.Threading.Tasks.Task<System.String> GetIDEVersion(System.Threading.CancellationToken token);
```


## Nested types

- `Game.Modding.Toolchain.Dependencies.RiderDependency+<>c`  

