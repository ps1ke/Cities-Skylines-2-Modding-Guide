# Colossal.Mono.Cecil.AssemblyResolutionException

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.IO.FileNotFoundException`  
**Implements:** `System.Runtime.Serialization.ISerializable`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed class AssemblyResolutionException : System.IO.FileNotFoundException, System.Runtime.Serialization.ISerializable
{
    private readonly Colossal.Mono.Cecil.AssemblyNameReference reference;

    public Colossal.Mono.Cecil.AssemblyNameReference AssemblyReference { get; }

    public AssemblyResolutionException(Colossal.Mono.Cecil.AssemblyNameReference reference);
    public AssemblyResolutionException(Colossal.Mono.Cecil.AssemblyNameReference reference, System.Exception innerException);
    private AssemblyResolutionException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context);

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

- `public AssemblyResolutionException(Colossal.Mono.Cecil.AssemblyNameReference reference)`  

```csharp
public AssemblyResolutionException(Colossal.Mono.Cecil.AssemblyNameReference reference);
```

- `public AssemblyResolutionException(Colossal.Mono.Cecil.AssemblyNameReference reference, System.Exception innerException)`  

```csharp
public AssemblyResolutionException(Colossal.Mono.Cecil.AssemblyNameReference reference, System.Exception innerException);
```

- `private AssemblyResolutionException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context)`  

```csharp
private AssemblyResolutionException(System.Runtime.Serialization.SerializationInfo info, System.Runtime.Serialization.StreamingContext context);
```


