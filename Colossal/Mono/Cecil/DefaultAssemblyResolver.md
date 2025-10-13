# Colossal.Mono.Cecil.DefaultAssemblyResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.BaseAssemblyResolver`  
**Implements:** `Colossal.Mono.Cecil.IAssemblyResolver`, `System.IDisposable`  

## Code

```csharp
public class DefaultAssemblyResolver : Colossal.Mono.Cecil.BaseAssemblyResolver, Colossal.Mono.Cecil.IAssemblyResolver, System.IDisposable
{
    private readonly System.Collections.Generic.IDictionary<System.String, Colossal.Mono.Cecil.AssemblyDefinition> cache;

    public DefaultAssemblyResolver();

    protected virtual System.Void Dispose(System.Boolean disposing);
    protected System.Void RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly);
    public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name);
}
```


## Fields

- `private readonly System.Collections.Generic.IDictionary<System.String, Colossal.Mono.Cecil.AssemblyDefinition> cache`  

```csharp
private readonly System.Collections.Generic.IDictionary<System.String, Colossal.Mono.Cecil.AssemblyDefinition> cache;
```


## Constructors

- `public DefaultAssemblyResolver()`  

```csharp
public DefaultAssemblyResolver();
```


## Methods

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  

```csharp
protected virtual System.Void Dispose(System.Boolean disposing);
```

- `protected RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly) : System.Void`  

```csharp
protected System.Void RegisterAssembly(Colossal.Mono.Cecil.AssemblyDefinition assembly);
```

- `public virtual Resolve(Colossal.Mono.Cecil.AssemblyNameReference name) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name);
```


