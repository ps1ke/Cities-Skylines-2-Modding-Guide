# Colossal.Mono.Cecil.AssemblyNameDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.AssemblyNameReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataScope`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class AssemblyNameDefinition : Colossal.Mono.Cecil.AssemblyNameReference, Colossal.Mono.Cecil.IMetadataScope, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    public System.Byte[] Hash { get; }

    internal AssemblyNameDefinition();
    public AssemblyNameDefinition(System.String name, System.Version version);

}
```


## Properties

- `public System.Byte[] Hash { get }`  

```csharp
public System.Byte[] Hash { get; }
```


## Constructors

- `internal AssemblyNameDefinition()`  

```csharp
internal AssemblyNameDefinition();
```

- `public AssemblyNameDefinition(System.String name, System.Version version)`  

```csharp
public AssemblyNameDefinition(System.String name, System.Version version);
```


