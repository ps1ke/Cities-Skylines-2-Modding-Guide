# Game.Modding.Toolchain.ToolchainException

**Assembly:** `Game`  
**Namespace:** `Game.Modding.Toolchain`  

**Type:** class public  

**Base:** `System.Exception`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public class ToolchainException : System.Exception, System.Runtime.Serialization.ISerializable
{
    private readonly Game.Modding.Toolchain.IToolchainDependency <source>k__BackingField;
    private readonly Game.Modding.Toolchain.ToolchainError <error>k__BackingField;

    public Game.Modding.Toolchain.IToolchainDependency source { get; }
    public Game.Modding.Toolchain.ToolchainError error { get; }

    public ToolchainException(Game.Modding.Toolchain.ToolchainError error, Game.Modding.Toolchain.IToolchainDependency source, System.String message, System.Exception innerException);
    public ToolchainException(Game.Modding.Toolchain.ToolchainError status, Game.Modding.Toolchain.IToolchainDependency source, System.Exception innerException);

}
```


## Fields

- `private readonly Game.Modding.Toolchain.IToolchainDependency <source>k__BackingField`  

```csharp
private readonly Game.Modding.Toolchain.IToolchainDependency <source>k__BackingField;
```

- `private readonly Game.Modding.Toolchain.ToolchainError <error>k__BackingField`  

```csharp
private readonly Game.Modding.Toolchain.ToolchainError <error>k__BackingField;
```


## Properties

- `public Game.Modding.Toolchain.IToolchainDependency source { get }`  

```csharp
public Game.Modding.Toolchain.IToolchainDependency source { get; }
```

- `public Game.Modding.Toolchain.ToolchainError error { get }`  

```csharp
public Game.Modding.Toolchain.ToolchainError error { get; }
```


## Constructors

- `public ToolchainException(Game.Modding.Toolchain.ToolchainError error, Game.Modding.Toolchain.IToolchainDependency source, System.String message = null, System.Exception innerException = null)`  

```csharp
public ToolchainException(Game.Modding.Toolchain.ToolchainError error, Game.Modding.Toolchain.IToolchainDependency source, System.String message, System.Exception innerException);
```

- `public ToolchainException(Game.Modding.Toolchain.ToolchainError status, Game.Modding.Toolchain.IToolchainDependency source, System.Exception innerException)`  

```csharp
public ToolchainException(Game.Modding.Toolchain.ToolchainError status, Game.Modding.Toolchain.IToolchainDependency source, System.Exception innerException);
```


