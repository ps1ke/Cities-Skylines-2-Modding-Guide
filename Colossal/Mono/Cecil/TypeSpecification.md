# Colossal.Mono.Cecil.TypeSpecification

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class abstract public  

**Base:** `Colossal.Mono.Cecil.TypeReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public abstract class TypeSpecification : Colossal.Mono.Cecil.TypeReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    private readonly Colossal.Mono.Cecil.TypeReference element_type;

    public Colossal.Mono.Cecil.TypeReference ElementType { get; }
    public System.String Name { get; set; }
    public System.String Namespace { get; set; }
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
    public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
    public System.String FullName { get; }
    public System.Boolean ContainsGenericParameter { get; }
    public Colossal.Mono.Cecil.MetadataType MetadataType { get; }

    internal TypeSpecification(Colossal.Mono.Cecil.TypeReference type);

    public virtual Colossal.Mono.Cecil.TypeReference GetElementType();
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.TypeReference element_type`  

```csharp
private readonly Colossal.Mono.Cecil.TypeReference element_type;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference ElementType { get }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ElementType { get; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String Namespace { get; set }`  

```csharp
public System.String Namespace { get; set; }
```

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```

- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataType MetadataType { get; }
```


## Constructors

- `internal TypeSpecification(Colossal.Mono.Cecil.TypeReference type)`  

```csharp
internal TypeSpecification(Colossal.Mono.Cecil.TypeReference type);
```


## Methods

- `public virtual GetElementType() : Colossal.Mono.Cecil.TypeReference`  

```csharp
public virtual Colossal.Mono.Cecil.TypeReference GetElementType();
```


