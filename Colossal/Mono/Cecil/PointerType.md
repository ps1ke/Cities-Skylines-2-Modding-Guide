# Colossal.Mono.Cecil.PointerType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public sealed class PointerType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    public System.String Name { get; }
    public System.String FullName { get; }
    public System.Boolean IsValueType { get; set; }
    public System.Boolean IsPointer { get; }

    public PointerType(Colossal.Mono.Cecil.TypeReference type);

}
```


## Properties

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public System.Boolean IsPointer { get }`  

```csharp
public System.Boolean IsPointer { get; }
```


## Constructors

- `public PointerType(Colossal.Mono.Cecil.TypeReference type)`  

```csharp
public PointerType(Colossal.Mono.Cecil.TypeReference type);
```


