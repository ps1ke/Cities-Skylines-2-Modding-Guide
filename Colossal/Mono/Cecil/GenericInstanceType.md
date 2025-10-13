# Colossal.Mono.Cecil.GenericInstanceType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IGenericInstance`  

## Code

```csharp
public sealed class GenericInstanceType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext, Colossal.Mono.Cecil.IGenericInstance
{
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> arguments;

    public System.Boolean HasGenericArguments { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get; }
    public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
    public System.String FullName { get; }
    public System.Boolean IsGenericInstance { get; }
    public System.Boolean ContainsGenericParameter { get; }
    private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get; }

    public GenericInstanceType(Colossal.Mono.Cecil.TypeReference type);
    internal GenericInstanceType(Colossal.Mono.Cecil.TypeReference type, System.Int32 arity);

}
```


## Fields

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> arguments`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> arguments;
```


## Properties

- `public System.Boolean HasGenericArguments { get }`  

```csharp
public System.Boolean HasGenericArguments { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeReference> GenericArguments { get; }
```

- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean IsGenericInstance { get }`  

```csharp
public System.Boolean IsGenericInstance { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```

- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  

```csharp
private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get; }
```


## Constructors

- `public GenericInstanceType(Colossal.Mono.Cecil.TypeReference type)`  

```csharp
public GenericInstanceType(Colossal.Mono.Cecil.TypeReference type);
```

- `internal GenericInstanceType(Colossal.Mono.Cecil.TypeReference type, System.Int32 arity)`  

```csharp
internal GenericInstanceType(Colossal.Mono.Cecil.TypeReference type, System.Int32 arity);
```


