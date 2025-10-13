# Colossal.Mono.Cecil.TypeReference

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `Colossal.Mono.Cecil.MemberReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`  

## Code

```csharp
public class TypeReference : Colossal.Mono.Cecil.MemberReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext
{
    private System.String namespace;
    private System.Boolean value_type;
    internal Colossal.Mono.Cecil.IMetadataScope scope;
    internal Colossal.Mono.Cecil.ModuleDefinition module;
    internal Colossal.Mono.Cecil.Metadata.ElementType etype;
    private System.String fullname;
    protected Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters;

    public System.String Name { get; set; }
    public System.String Namespace { get; set; }
    public System.Boolean IsValueType { get; set; }
    public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
    internal Colossal.Mono.Cecil.TypeReferenceProjection WindowsRuntimeProjection { internal get; internal set; }
    private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get; }
    private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get; }
    private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get; }
    public System.Boolean HasGenericParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
    public System.Boolean IsNested { get; }
    public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
    public System.String FullName { get; }
    public System.Boolean IsByReference { get; }
    public System.Boolean IsPointer { get; }
    public System.Boolean IsSentinel { get; }
    public System.Boolean IsArray { get; }
    public System.Boolean IsGenericParameter { get; }
    public System.Boolean IsGenericInstance { get; }
    public System.Boolean IsRequiredModifier { get; }
    public System.Boolean IsOptionalModifier { get; }
    public System.Boolean IsPinned { get; }
    public System.Boolean IsFunctionPointer { get; }
    public System.Boolean IsPrimitive { get; }
    public Colossal.Mono.Cecil.MetadataType MetadataType { get; }

    protected TypeReference(System.String namespace, System.String name);
    public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope);
    public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope, System.Boolean valueType);

    protected virtual System.Void ClearFullName();
    public virtual Colossal.Mono.Cecil.TypeReference GetElementType();
    public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
    protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
}
```


## Fields

- `private System.String namespace`  

```csharp
private System.String namespace;
```

- `private System.Boolean value_type`  

```csharp
private System.Boolean value_type;
```

- `internal Colossal.Mono.Cecil.IMetadataScope scope`  

```csharp
internal Colossal.Mono.Cecil.IMetadataScope scope;
```

- `internal Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
internal Colossal.Mono.Cecil.ModuleDefinition module;
```

- `internal Colossal.Mono.Cecil.Metadata.ElementType etype`  

```csharp
internal Colossal.Mono.Cecil.Metadata.ElementType etype;
```

- `private System.String fullname`  

```csharp
private System.String fullname;
```

- `protected Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters`  

```csharp
protected Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> generic_parameters;
```


## Properties

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.String Namespace { get; set }`  

```csharp
public System.String Namespace { get; set; }
```

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public Colossal.Mono.Cecil.ModuleDefinition Module { get }`  

```csharp
public Colossal.Mono.Cecil.ModuleDefinition Module { get; }
```

- `internal Colossal.Mono.Cecil.TypeReferenceProjection WindowsRuntimeProjection { internal get; internal set }`  

```csharp
internal Colossal.Mono.Cecil.TypeReferenceProjection WindowsRuntimeProjection { internal get; internal set; }
```

- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get }`  

```csharp
private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Type { private get; }
```

- `private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get }`  

```csharp
private Colossal.Mono.Cecil.IGenericParameterProvider Colossal.Mono.Cecil.IGenericContext.Method { private get; }
```

- `private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get }`  

```csharp
private Colossal.Mono.Cecil.GenericParameterType Colossal.Mono.Cecil.IGenericParameterProvider.GenericParameterType { private get; }
```

- `public System.Boolean HasGenericParameters { get }`  

```csharp
public System.Boolean HasGenericParameters { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
```

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
```

- `public System.Boolean IsNested { get }`  

```csharp
public System.Boolean IsNested { get; }
```

- `public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference DeclaringType { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```

- `public System.Boolean IsByReference { get }`  

```csharp
public System.Boolean IsByReference { get; }
```

- `public System.Boolean IsPointer { get }`  

```csharp
public System.Boolean IsPointer { get; }
```

- `public System.Boolean IsSentinel { get }`  

```csharp
public System.Boolean IsSentinel { get; }
```

- `public System.Boolean IsArray { get }`  

```csharp
public System.Boolean IsArray { get; }
```

- `public System.Boolean IsGenericParameter { get }`  

```csharp
public System.Boolean IsGenericParameter { get; }
```

- `public System.Boolean IsGenericInstance { get }`  

```csharp
public System.Boolean IsGenericInstance { get; }
```

- `public System.Boolean IsRequiredModifier { get }`  

```csharp
public System.Boolean IsRequiredModifier { get; }
```

- `public System.Boolean IsOptionalModifier { get }`  

```csharp
public System.Boolean IsOptionalModifier { get; }
```

- `public System.Boolean IsPinned { get }`  

```csharp
public System.Boolean IsPinned { get; }
```

- `public System.Boolean IsFunctionPointer { get }`  

```csharp
public System.Boolean IsFunctionPointer { get; }
```

- `public System.Boolean IsPrimitive { get }`  

```csharp
public System.Boolean IsPrimitive { get; }
```

- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataType MetadataType { get; }
```


## Constructors

- `protected TypeReference(System.String namespace, System.String name)`  

```csharp
protected TypeReference(System.String namespace, System.String name);
```

- `public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope)`  

```csharp
public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope);
```

- `public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope, System.Boolean valueType)`  

```csharp
public TypeReference(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope, System.Boolean valueType);
```


## Methods

- `protected virtual ClearFullName() : System.Void`  

```csharp
protected virtual System.Void ClearFullName();
```

- `public virtual GetElementType() : Colossal.Mono.Cecil.TypeReference`  

```csharp
public virtual Colossal.Mono.Cecil.TypeReference GetElementType();
```

- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
```

- `protected virtual ResolveDefinition() : Colossal.Mono.Cecil.IMemberDefinition`  

```csharp
protected virtual Colossal.Mono.Cecil.IMemberDefinition ResolveDefinition();
```


