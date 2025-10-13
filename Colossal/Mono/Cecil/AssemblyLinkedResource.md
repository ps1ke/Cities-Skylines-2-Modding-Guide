# Colossal.Mono.Cecil.AssemblyLinkedResource

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Resource`  

## Code

```csharp
public sealed class AssemblyLinkedResource : Colossal.Mono.Cecil.Resource
{
    private Colossal.Mono.Cecil.AssemblyNameReference reference;

    public Colossal.Mono.Cecil.AssemblyNameReference Assembly { get; set; }
    public Colossal.Mono.Cecil.ResourceType ResourceType { get; }

    public AssemblyLinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags);
    public AssemblyLinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags, Colossal.Mono.Cecil.AssemblyNameReference reference);

}
```


## Fields

- `private Colossal.Mono.Cecil.AssemblyNameReference reference`  

```csharp
private Colossal.Mono.Cecil.AssemblyNameReference reference;
```


## Properties

- `public Colossal.Mono.Cecil.AssemblyNameReference Assembly { get; set }`  

```csharp
public Colossal.Mono.Cecil.AssemblyNameReference Assembly { get; set; }
```

- `public Colossal.Mono.Cecil.ResourceType ResourceType { get }`  

```csharp
public Colossal.Mono.Cecil.ResourceType ResourceType { get; }
```


## Constructors

- `public AssemblyLinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags)`  

```csharp
public AssemblyLinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags);
```

- `public AssemblyLinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags, Colossal.Mono.Cecil.AssemblyNameReference reference)`  

```csharp
public AssemblyLinkedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes flags, Colossal.Mono.Cecil.AssemblyNameReference reference);
```


