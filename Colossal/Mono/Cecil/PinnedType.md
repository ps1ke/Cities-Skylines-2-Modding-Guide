# Colossal.Mono.Cecil.PinnedType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public sealed class PinnedType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    public System.Boolean IsValueType { get; set; }
    public System.Boolean IsPinned { get; }

    public PinnedType(Colossal.Mono.Cecil.TypeReference type);

}
```


## Properties

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public System.Boolean IsPinned { get }`  

```csharp
public System.Boolean IsPinned { get; }
```


## Constructors

- `public PinnedType(Colossal.Mono.Cecil.TypeReference type)`  

```csharp
public PinnedType(Colossal.Mono.Cecil.TypeReference type);
```


