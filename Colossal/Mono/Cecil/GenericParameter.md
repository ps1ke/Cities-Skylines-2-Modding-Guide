# Colossal.Mono.Cecil.GenericParameter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.ICustomAttributeProvider`  

## Code

```csharp
public sealed class GenericParameter : Colossal.Mono.Cecil.TypeReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext, Colossal.Mono.Cecil.ICustomAttributeProvider
{
    internal System.Int32 position;
    internal Colossal.Mono.Cecil.GenericParameterType type;
    internal Colossal.Mono.Cecil.IGenericParameterProvider owner;
    private System.UInt16 attributes;
    private Colossal.Mono.Cecil.GenericParameterConstraintCollection constraints;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;

    public Colossal.Mono.Cecil.GenericParameterAttributes Attributes { get; set; }
    public System.Int32 Position { get; }
    public Colossal.Mono.Cecil.GenericParameterType Type { get; }
    public Colossal.Mono.Cecil.IGenericParameterProvider Owner { get; }
    public System.Boolean HasConstraints { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameterConstraint> Constraints { get; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
    public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
    public Colossal.Mono.Cecil.MethodReference DeclaringMethod { get; }
    public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
    public System.String Name { get; }
    public System.String Namespace { get; set; }
    public System.String FullName { get; }
    public System.Boolean IsGenericParameter { get; }
    public System.Boolean ContainsGenericParameter { get; }
    public Colossal.Mono.Cecil.MetadataType MetadataType { get; }
    public System.Boolean IsNonVariant { get; set; }
    public System.Boolean IsCovariant { get; set; }
    public System.Boolean IsContravariant { get; set; }
    public System.Boolean HasReferenceTypeConstraint { get; set; }
    public System.Boolean HasNotNullableValueTypeConstraint { get; set; }
    public System.Boolean HasDefaultConstructorConstraint { get; set; }

    public GenericParameter(Colossal.Mono.Cecil.IGenericParameterProvider owner);
    public GenericParameter(System.String name, Colossal.Mono.Cecil.IGenericParameterProvider owner);
    internal GenericParameter(System.Int32 position, Colossal.Mono.Cecil.GenericParameterType type, Colossal.Mono.Cecil.ModuleDefinition module);

    private static Colossal.Mono.Cecil.Metadata.ElementType ConvertGenericParameterType(Colossal.Mono.Cecil.GenericParameterType type);
    public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
}
```


## Fields

- `internal System.Int32 position`  

```csharp
internal System.Int32 position;
```

- `internal Colossal.Mono.Cecil.GenericParameterType type`  

```csharp
internal Colossal.Mono.Cecil.GenericParameterType type;
```

- `internal Colossal.Mono.Cecil.IGenericParameterProvider owner`  

```csharp
internal Colossal.Mono.Cecil.IGenericParameterProvider owner;
```

- `private System.UInt16 attributes`  

```csharp
private System.UInt16 attributes;
```

- `private Colossal.Mono.Cecil.GenericParameterConstraintCollection constraints`  

```csharp
private Colossal.Mono.Cecil.GenericParameterConstraintCollection constraints;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```


## Properties

- `public Colossal.Mono.Cecil.GenericParameterAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.GenericParameterAttributes Attributes { get; set; }
```

- `public System.Int32 Position { get }`  

```csharp
public System.Int32 Position { get; }
```

- `public Colossal.Mono.Cecil.GenericParameterType Type { get }`  

```csharp
public Colossal.Mono.Cecil.GenericParameterType Type { get; }
```

- `public Colossal.Mono.Cecil.IGenericParameterProvider Owner { get }`  

```csharp
public Colossal.Mono.Cecil.IGenericParameterProvider Owner { get; }
```

- `public System.Boolean HasConstraints { get }`  

```csharp
public System.Boolean HasConstraints { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameterConstraint> Constraints { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameterConstraint> Constraints { get; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
```

- `public Colossal.Mono.Cecil.MethodReference DeclaringMethod { get }`  

```csharp
public Colossal.Mono.Cecil.MethodReference DeclaringMethod { get; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
```

- `public System.String Name { get }`  

```csharp
public System.String Name { get; }
```

- `public System.String Namespace { get; set }`  

```csharp
public System.String Namespace { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean IsGenericParameter { get }`  

```csharp
public System.Boolean IsGenericParameter { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```

- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataType MetadataType { get; }
```

- `public System.Boolean IsNonVariant { get; set }`  

```csharp
public System.Boolean IsNonVariant { get; set; }
```

- `public System.Boolean IsCovariant { get; set }`  

```csharp
public System.Boolean IsCovariant { get; set; }
```

- `public System.Boolean IsContravariant { get; set }`  

```csharp
public System.Boolean IsContravariant { get; set; }
```

- `public System.Boolean HasReferenceTypeConstraint { get; set }`  

```csharp
public System.Boolean HasReferenceTypeConstraint { get; set; }
```

- `public System.Boolean HasNotNullableValueTypeConstraint { get; set }`  

```csharp
public System.Boolean HasNotNullableValueTypeConstraint { get; set; }
```

- `public System.Boolean HasDefaultConstructorConstraint { get; set }`  

```csharp
public System.Boolean HasDefaultConstructorConstraint { get; set; }
```


## Constructors

- `public GenericParameter(Colossal.Mono.Cecil.IGenericParameterProvider owner)`  

```csharp
public GenericParameter(Colossal.Mono.Cecil.IGenericParameterProvider owner);
```

- `public GenericParameter(System.String name, Colossal.Mono.Cecil.IGenericParameterProvider owner)`  

```csharp
public GenericParameter(System.String name, Colossal.Mono.Cecil.IGenericParameterProvider owner);
```

- `internal GenericParameter(System.Int32 position, Colossal.Mono.Cecil.GenericParameterType type, Colossal.Mono.Cecil.ModuleDefinition module)`  

```csharp
internal GenericParameter(System.Int32 position, Colossal.Mono.Cecil.GenericParameterType type, Colossal.Mono.Cecil.ModuleDefinition module);
```


## Methods

- `private static ConvertGenericParameterType(Colossal.Mono.Cecil.GenericParameterType type) : Colossal.Mono.Cecil.Metadata.ElementType`  

```csharp
private static Colossal.Mono.Cecil.Metadata.ElementType ConvertGenericParameterType(Colossal.Mono.Cecil.GenericParameterType type);
```

- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
```


## Nested types

- `Colossal.Mono.Cecil.GenericParameter+<>c`  

