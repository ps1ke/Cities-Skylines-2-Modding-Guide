# Colossal.Mono.Cecil.GenericParameterConstraint

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class GenericParameterConstraint : Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal Colossal.Mono.Cecil.GenericParameter generic_parameter;
    internal Colossal.Mono.Cecil.MetadataToken token;
    private Colossal.Mono.Cecil.TypeReference constraint_type;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;

    public Colossal.Mono.Cecil.TypeReference ConstraintType { get; set; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }

    internal GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType, Colossal.Mono.Cecil.MetadataToken token);
    public GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType);

}
```


## Fields

- `internal Colossal.Mono.Cecil.GenericParameter generic_parameter`  

```csharp
internal Colossal.Mono.Cecil.GenericParameter generic_parameter;
```

- `internal Colossal.Mono.Cecil.MetadataToken token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken token;
```

- `private Colossal.Mono.Cecil.TypeReference constraint_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference constraint_type;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference ConstraintType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference ConstraintType { get; set; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```


## Constructors

- `internal GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType, Colossal.Mono.Cecil.MetadataToken token)`  

```csharp
internal GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType, Colossal.Mono.Cecil.MetadataToken token);
```

- `public GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType)`  

```csharp
public GenericParameterConstraint(Colossal.Mono.Cecil.TypeReference constraintType);
```


