# Colossal.Mono.Cecil.AssemblyResolveEventArgs

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.EventArgs`  

## Code

```csharp
public sealed class AssemblyResolveEventArgs : System.EventArgs
{
    private readonly Colossal.Mono.Cecil.AssemblyNameReference reference;

    public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get; }

    public AssemblyResolveEventArgs(Colossal.Mono.Cecil.AssemblyNameReference reference);

}
```


## Fields

- `private readonly Colossal.Mono.Cecil.AssemblyNameReference reference`  

```csharp
private readonly Colossal.Mono.Cecil.AssemblyNameReference reference;
```


## Properties

- `public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get }`  

```csharp
public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get; }
```


## Constructors

- `public AssemblyResolveEventArgs(Colossal.Mono.Cecil.AssemblyNameReference reference)`  

```csharp
public AssemblyResolveEventArgs(Colossal.Mono.Cecil.AssemblyNameReference reference);
```


