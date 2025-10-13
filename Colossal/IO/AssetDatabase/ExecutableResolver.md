# Colossal.IO.AssetDatabase.ExecutableAsset+ExecutableResolver

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.BaseAssemblyResolver`  
**Implements:** `Colossal.Mono.Cecil.IAssemblyResolver`, `System.IDisposable`  

## Code

```csharp
public class ExecutableResolver : Colossal.Mono.Cecil.BaseAssemblyResolver, Colossal.Mono.Cecil.IAssemblyResolver, System.IDisposable
{
    private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.Dictionary<System.Version, Colossal.Mono.Cecil.AssemblyDefinition>> m_Cache;
    private static System.String[] m_SearchDirectories;

    public ExecutableResolver();

    public System.Void RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly);
    public System.Void RegisterAsset(Colossal.IO.AssetDatabase.ExecutableAsset asset);
    public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference toResolve);
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.Dictionary<System.Version, Colossal.Mono.Cecil.AssemblyDefinition>> m_Cache`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.Dictionary<System.Version, Colossal.Mono.Cecil.AssemblyDefinition>> m_Cache;
```

- `private static System.String[] m_SearchDirectories`  

```csharp
private static System.String[] m_SearchDirectories;
```


## Constructors

- `public ExecutableResolver()`  

```csharp
public ExecutableResolver();
```


## Methods

- `public RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly) : System.Void`  

```csharp
public System.Void RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly);
```

- `public RegisterAsset(Colossal.IO.AssetDatabase.ExecutableAsset asset) : System.Void`  

```csharp
public System.Void RegisterAsset(Colossal.IO.AssetDatabase.ExecutableAsset asset);
```

- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference toResolve) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference toResolve);
```


## Nested types

- `Colossal.IO.AssetDatabase.ExecutableAsset+ExecutableResolver+<>c`  

