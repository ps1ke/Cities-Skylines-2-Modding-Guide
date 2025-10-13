# Colossal.Mono.Cecil.ArrayType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeSpecification`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public sealed class ArrayType : Colossal.Mono.Cecil.TypeSpecification, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ArrayDimension> dimensions;

    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ArrayDimension> Dimensions { get; }
    public System.Int32 Rank { get; }
    public System.Boolean IsVector { get; }
    public System.Boolean IsValueType { get; set; }
    public System.String Name { get; }
    public System.String FullName { get; }
    private System.String Suffix { private get; }
    public System.Boolean IsArray { get; }

    public ArrayType(Colossal.Mono.Cecil.TypeReference type);
    public ArrayType(Colossal.Mono.Cecil.TypeReference type, System.Int32 rank);

}
```


## Fields

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ArrayDimension> dimensions`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ArrayDimension> dimensions;
```


## Properties

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ArrayDimension> Dimensions { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.ArrayDimension> Dimensions { get; }
```

- `public System.Int32 Rank { get }`  

```csharp
public System.Int32 Rank { get; }
```

- `public System.Boolean IsVector { get }`  

```csharp
public System.Boolean IsVector { get; }
```

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `private System.String Suffix { private get }`  

```csharp
private System.String Suffix { private get; }
```

- `public System.Boolean IsArray { get }`  

```csharp
public System.Boolean IsArray { get; }
```


## Constructors

- `public ArrayType(Colossal.Mono.Cecil.TypeReference type)`  

```csharp
public ArrayType(Colossal.Mono.Cecil.TypeReference type);
```

- `public ArrayType(Colossal.Mono.Cecil.TypeReference type, System.Int32 rank)`  

```csharp
public ArrayType(Colossal.Mono.Cecil.TypeReference type, System.Int32 rank);
```


