# Colossal.Mono.Cecil.FieldReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public class FieldReference : Colossal.Mono.Cecil.MemberReference, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private Colossal.Mono.Cecil.TypeReference field_type;

    public Colossal.Mono.Cecil.TypeReference FieldType { get; set; }
    public System.String FullName { get; }
    public System.Boolean ContainsGenericParameter { get; }

    internal FieldReference();
    public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType);
    public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType, Colossal.Mono.Cecil.TypeReference declaringType);

    public virtual Colossal.Mono.Cecil.FieldDefinition Resolve();
    protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
}
```


## Fields

- `private Colossal.Mono.Cecil.TypeReference field_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference field_type;
```


## Properties

- `public Colossal.Mono.Cecil.TypeReference FieldType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference FieldType { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean ContainsGenericParameter { get }`  

```csharp
public System.Boolean ContainsGenericParameter { get; }
```


## Constructors

- `internal FieldReference()`  

```csharp
internal FieldReference();
```

- `public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType)`  

```csharp
public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType);
```

- `public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType, Colossal.Mono.Cecil.TypeReference declaringType)`  

```csharp
public FieldReference(System.String name, Colossal.Mono.Cecil.TypeReference fieldType, Colossal.Mono.Cecil.TypeReference declaringType);
```


## Methods

- `public virtual Resolve() : Colossal.Mono.Cecil.FieldDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.FieldDefinition Resolve();
```

- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
```


