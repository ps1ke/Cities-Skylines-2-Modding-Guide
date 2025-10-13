# Colossal.Mono.Cecil.ExportedType

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class ExportedType : Colossal.Mono.Cecil.IMetadataTokenProvider
{
    private System.String namespace;
    private System.String name;
    private System.UInt32 attributes;
    private Colossal.Mono.Cecil.IMetadataScope scope;
    private Colossal.Mono.Cecil.ModuleDefinition module;
    private System.Int32 identifier;
    private Colossal.Mono.Cecil.ExportedType declaring_type;
    internal Colossal.Mono.Cecil.MetadataToken token;

    public System.String Namespace { get; set; }
    public System.String Name { get; set; }
    public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set; }
    public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
    public Colossal.Mono.Cecil.ExportedType DeclaringType { get; set; }
    public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
    public System.Int32 Identifier { get; set; }
    public System.Boolean IsNotPublic { get; set; }
    public System.Boolean IsPublic { get; set; }
    public System.Boolean IsNestedPublic { get; set; }
    public System.Boolean IsNestedPrivate { get; set; }
    public System.Boolean IsNestedFamily { get; set; }
    public System.Boolean IsNestedAssembly { get; set; }
    public System.Boolean IsNestedFamilyAndAssembly { get; set; }
    public System.Boolean IsNestedFamilyOrAssembly { get; set; }
    public System.Boolean IsAutoLayout { get; set; }
    public System.Boolean IsSequentialLayout { get; set; }
    public System.Boolean IsExplicitLayout { get; set; }
    public System.Boolean IsClass { get; set; }
    public System.Boolean IsInterface { get; set; }
    public System.Boolean IsAbstract { get; set; }
    public System.Boolean IsSealed { get; set; }
    public System.Boolean IsSpecialName { get; set; }
    public System.Boolean IsImport { get; set; }
    public System.Boolean IsSerializable { get; set; }
    public System.Boolean IsAnsiClass { get; set; }
    public System.Boolean IsUnicodeClass { get; set; }
    public System.Boolean IsAutoClass { get; set; }
    public System.Boolean IsBeforeFieldInit { get; set; }
    public System.Boolean IsRuntimeSpecialName { get; set; }
    public System.Boolean HasSecurity { get; set; }
    public System.Boolean IsForwarder { get; set; }
    public System.String FullName { get; }

    public ExportedType(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope);

    internal Colossal.Mono.Cecil.TypeReference CreateReference();
    public Colossal.Mono.Cecil.TypeDefinition Resolve();
    public virtual System.String ToString();
}
```


## Fields

- `private System.String namespace`  

```csharp
private System.String namespace;
```

- `private System.String name`  

```csharp
private System.String name;
```

- `private System.UInt32 attributes`  

```csharp
private System.UInt32 attributes;
```

- `private Colossal.Mono.Cecil.IMetadataScope scope`  

```csharp
private Colossal.Mono.Cecil.IMetadataScope scope;
```

- `private Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private System.Int32 identifier`  

```csharp
private System.Int32 identifier;
```

- `private Colossal.Mono.Cecil.ExportedType declaring_type`  

```csharp
private Colossal.Mono.Cecil.ExportedType declaring_type;
```

- `internal Colossal.Mono.Cecil.MetadataToken token`  

```csharp
internal Colossal.Mono.Cecil.MetadataToken token;
```


## Properties

- `public System.String Namespace { get; set }`  

```csharp
public System.String Namespace { get; set; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set; }
```

- `public Colossal.Mono.Cecil.IMetadataScope Scope { get; set }`  

```csharp
public Colossal.Mono.Cecil.IMetadataScope Scope { get; set; }
```

- `public Colossal.Mono.Cecil.ExportedType DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.ExportedType DeclaringType { get; set; }
```

- `public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set }`  

```csharp
public Colossal.Mono.Cecil.MetadataToken MetadataToken { get; set; }
```

- `public System.Int32 Identifier { get; set }`  

```csharp
public System.Int32 Identifier { get; set; }
```

- `public System.Boolean IsNotPublic { get; set }`  

```csharp
public System.Boolean IsNotPublic { get; set; }
```

- `public System.Boolean IsPublic { get; set }`  

```csharp
public System.Boolean IsPublic { get; set; }
```

- `public System.Boolean IsNestedPublic { get; set }`  

```csharp
public System.Boolean IsNestedPublic { get; set; }
```

- `public System.Boolean IsNestedPrivate { get; set }`  

```csharp
public System.Boolean IsNestedPrivate { get; set; }
```

- `public System.Boolean IsNestedFamily { get; set }`  

```csharp
public System.Boolean IsNestedFamily { get; set; }
```

- `public System.Boolean IsNestedAssembly { get; set }`  

```csharp
public System.Boolean IsNestedAssembly { get; set; }
```

- `public System.Boolean IsNestedFamilyAndAssembly { get; set }`  

```csharp
public System.Boolean IsNestedFamilyAndAssembly { get; set; }
```

- `public System.Boolean IsNestedFamilyOrAssembly { get; set }`  

```csharp
public System.Boolean IsNestedFamilyOrAssembly { get; set; }
```

- `public System.Boolean IsAutoLayout { get; set }`  

```csharp
public System.Boolean IsAutoLayout { get; set; }
```

- `public System.Boolean IsSequentialLayout { get; set }`  

```csharp
public System.Boolean IsSequentialLayout { get; set; }
```

- `public System.Boolean IsExplicitLayout { get; set }`  

```csharp
public System.Boolean IsExplicitLayout { get; set; }
```

- `public System.Boolean IsClass { get; set }`  

```csharp
public System.Boolean IsClass { get; set; }
```

- `public System.Boolean IsInterface { get; set }`  

```csharp
public System.Boolean IsInterface { get; set; }
```

- `public System.Boolean IsAbstract { get; set }`  

```csharp
public System.Boolean IsAbstract { get; set; }
```

- `public System.Boolean IsSealed { get; set }`  

```csharp
public System.Boolean IsSealed { get; set; }
```

- `public System.Boolean IsSpecialName { get; set }`  

```csharp
public System.Boolean IsSpecialName { get; set; }
```

- `public System.Boolean IsImport { get; set }`  

```csharp
public System.Boolean IsImport { get; set; }
```

- `public System.Boolean IsSerializable { get; set }`  

```csharp
public System.Boolean IsSerializable { get; set; }
```

- `public System.Boolean IsAnsiClass { get; set }`  

```csharp
public System.Boolean IsAnsiClass { get; set; }
```

- `public System.Boolean IsUnicodeClass { get; set }`  

```csharp
public System.Boolean IsUnicodeClass { get; set; }
```

- `public System.Boolean IsAutoClass { get; set }`  

```csharp
public System.Boolean IsAutoClass { get; set; }
```

- `public System.Boolean IsBeforeFieldInit { get; set }`  

```csharp
public System.Boolean IsBeforeFieldInit { get; set; }
```

- `public System.Boolean IsRuntimeSpecialName { get; set }`  

```csharp
public System.Boolean IsRuntimeSpecialName { get; set; }
```

- `public System.Boolean HasSecurity { get; set }`  

```csharp
public System.Boolean HasSecurity { get; set; }
```

- `public System.Boolean IsForwarder { get; set }`  

```csharp
public System.Boolean IsForwarder { get; set; }
```

- `public System.String FullName { get }`  

```csharp
public System.String FullName { get; }
```


## Constructors

- `public ExportedType(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope)`  

```csharp
public ExportedType(System.String namespace, System.String name, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.IMetadataScope scope);
```


## Methods

- `internal CreateReference() : Colossal.Mono.Cecil.TypeReference`  

```csharp
internal Colossal.Mono.Cecil.TypeReference CreateReference();
```

- `public Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition Resolve();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


