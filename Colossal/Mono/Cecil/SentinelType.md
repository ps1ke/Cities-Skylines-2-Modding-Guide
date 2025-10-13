# Colossal.Mono.Cecil.SentinelType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public sealed class SentinelType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    public System.Boolean IsValueType { get; set; }
    public System.Boolean IsSentinel { get; }

    public SentinelType(Colossal.Mono.Cecil.TypeReference type);

}
```


## Properties

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public System.Boolean IsSentinel { get }`  

```csharp
public System.Boolean IsSentinel { get; }
```


## Constructors

- `public SentinelType(Colossal.Mono.Cecil.TypeReference type)`  

```csharp
public SentinelType(Colossal.Mono.Cecil.TypeReference type);
```


