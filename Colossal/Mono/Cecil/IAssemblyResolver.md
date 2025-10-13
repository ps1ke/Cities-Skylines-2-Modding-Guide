# Colossal.Mono.Cecil.IAssemblyResolver

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IAssemblyResolver : System.IDisposable
{
    public abstract Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name);
    public abstract Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters);
}
```


## Methods

- `public abstract Resolve(Colossal.Mono.Cecil.AssemblyNameReference name) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name);
```

- `public abstract Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters) : Colossal.Mono.Cecil.AssemblyDefinition`  

```csharp
public abstract Colossal.Mono.Cecil.AssemblyDefinition Resolve(Colossal.Mono.Cecil.AssemblyNameReference name, Colossal.Mono.Cecil.ReaderParameters parameters);
```


