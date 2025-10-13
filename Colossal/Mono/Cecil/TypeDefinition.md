# Colossal.Mono.Cecil.TypeDefinition

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.TypeReference`  
**Implements:** `Colossal.Mono.Cecil.IMetadataTokenProvider`, `Colossal.Mono.Cecil.IGenericParameterProvider`, `Colossal.Mono.Cecil.IGenericContext`, `Colossal.Mono.Cecil.IMemberDefinition`, `Colossal.Mono.Cecil.ICustomAttributeProvider`, `Colossal.Mono.Cecil.ISecurityDeclarationProvider`  

## Code

```csharp
public sealed class TypeDefinition : Colossal.Mono.Cecil.TypeReference, Colossal.Mono.Cecil.IMetadataTokenProvider, Colossal.Mono.Cecil.IGenericParameterProvider, Colossal.Mono.Cecil.IGenericContext, Colossal.Mono.Cecil.IMemberDefinition, Colossal.Mono.Cecil.ICustomAttributeProvider, Colossal.Mono.Cecil.ISecurityDeclarationProvider
{
    private System.UInt32 attributes;
    private Colossal.Mono.Cecil.TypeReference base_type;
    internal Colossal.Mono.Cecil.Range fields_range;
    internal Colossal.Mono.Cecil.Range methods_range;
    private System.Int16 packing_size;
    private System.Int32 class_size;
    private Colossal.Mono.Cecil.InterfaceImplementationCollection interfaces;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> nested_types;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> events;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> properties;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations;

    public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set; }
    public Colossal.Mono.Cecil.TypeReference BaseType { get; set; }
    public System.String Name { get; set; }
    public System.Boolean HasLayoutInfo { get; }
    public System.Int16 PackingSize { get; set; }
    public System.Int32 ClassSize { get; set; }
    public System.Boolean HasInterfaces { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.InterfaceImplementation> Interfaces { get; }
    public System.Boolean HasNestedTypes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> NestedTypes { get; }
    public System.Boolean HasMethods { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> Methods { get; }
    public System.Boolean HasFields { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> Fields { get; }
    public System.Boolean HasEvents { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> Events { get; }
    public System.Boolean HasProperties { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> Properties { get; }
    public System.Boolean HasSecurityDeclarations { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get; }
    public System.Boolean HasCustomAttributes { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
    public System.Boolean HasGenericParameters { get; }
    public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
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
    public System.Boolean IsWindowsRuntime { get; set; }
    public System.Boolean IsAnsiClass { get; set; }
    public System.Boolean IsUnicodeClass { get; set; }
    public System.Boolean IsAutoClass { get; set; }
    public System.Boolean IsBeforeFieldInit { get; set; }
    public System.Boolean IsRuntimeSpecialName { get; set; }
    public System.Boolean HasSecurity { get; set; }
    public System.Boolean IsEnum { get; }
    public System.Boolean IsValueType { get; set; }
    public System.Boolean IsPrimitive { get; }
    public Colossal.Mono.Cecil.MetadataType MetadataType { get; }
    public System.Boolean IsDefinition { get; }
    public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
    internal Colossal.Mono.Cecil.TypeDefinitionProjection WindowsRuntimeProjection { internal get; internal set; }

    public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes);
    public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes, Colossal.Mono.Cecil.TypeReference baseType);

    protected virtual System.Void ClearFullName();
    public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
    private System.Void ResolveLayout();
}
```


## Fields

- `private System.UInt32 attributes`  

```csharp
private System.UInt32 attributes;
```

- `private Colossal.Mono.Cecil.TypeReference base_type`  

```csharp
private Colossal.Mono.Cecil.TypeReference base_type;
```

- `internal Colossal.Mono.Cecil.Range fields_range`  

```csharp
internal Colossal.Mono.Cecil.Range fields_range;
```

- `internal Colossal.Mono.Cecil.Range methods_range`  

```csharp
internal Colossal.Mono.Cecil.Range methods_range;
```

- `private System.Int16 packing_size`  

```csharp
private System.Int16 packing_size;
```

- `private System.Int32 class_size`  

```csharp
private System.Int32 class_size;
```

- `private Colossal.Mono.Cecil.InterfaceImplementationCollection interfaces`  

```csharp
private Colossal.Mono.Cecil.InterfaceImplementationCollection interfaces;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> nested_types`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> nested_types;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> methods;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> fields;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> events`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> events;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> properties`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> properties;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> custom_attributes;
```

- `private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> security_declarations;
```


## Properties

- `public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeAttributes Attributes { get; set; }
```

- `public Colossal.Mono.Cecil.TypeReference BaseType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeReference BaseType { get; set; }
```

- `public System.String Name { get; set }`  

```csharp
public System.String Name { get; set; }
```

- `public System.Boolean HasLayoutInfo { get }`  

```csharp
public System.Boolean HasLayoutInfo { get; }
```

- `public System.Int16 PackingSize { get; set }`  

```csharp
public System.Int16 PackingSize { get; set; }
```

- `public System.Int32 ClassSize { get; set }`  

```csharp
public System.Int32 ClassSize { get; set; }
```

- `public System.Boolean HasInterfaces { get }`  

```csharp
public System.Boolean HasInterfaces { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.InterfaceImplementation> Interfaces { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.InterfaceImplementation> Interfaces { get; }
```

- `public System.Boolean HasNestedTypes { get }`  

```csharp
public System.Boolean HasNestedTypes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> NestedTypes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.TypeDefinition> NestedTypes { get; }
```

- `public System.Boolean HasMethods { get }`  

```csharp
public System.Boolean HasMethods { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> Methods { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.MethodDefinition> Methods { get; }
```

- `public System.Boolean HasFields { get }`  

```csharp
public System.Boolean HasFields { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> Fields { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.FieldDefinition> Fields { get; }
```

- `public System.Boolean HasEvents { get }`  

```csharp
public System.Boolean HasEvents { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> Events { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.EventDefinition> Events { get; }
```

- `public System.Boolean HasProperties { get }`  

```csharp
public System.Boolean HasProperties { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> Properties { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.PropertyDefinition> Properties { get; }
```

- `public System.Boolean HasSecurityDeclarations { get }`  

```csharp
public System.Boolean HasSecurityDeclarations { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.SecurityDeclaration> SecurityDeclarations { get; }
```

- `public System.Boolean HasCustomAttributes { get }`  

```csharp
public System.Boolean HasCustomAttributes { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.CustomAttribute> CustomAttributes { get; }
```

- `public System.Boolean HasGenericParameters { get }`  

```csharp
public System.Boolean HasGenericParameters { get; }
```

- `public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get }`  

```csharp
public Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.GenericParameter> GenericParameters { get; }
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

- `public System.Boolean IsWindowsRuntime { get; set }`  

```csharp
public System.Boolean IsWindowsRuntime { get; set; }
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

- `public System.Boolean IsEnum { get }`  

```csharp
public System.Boolean IsEnum { get; }
```

- `public System.Boolean IsValueType { get; set }`  

```csharp
public System.Boolean IsValueType { get; set; }
```

- `public System.Boolean IsPrimitive { get }`  

```csharp
public System.Boolean IsPrimitive { get; }
```

- `public Colossal.Mono.Cecil.MetadataType MetadataType { get }`  

```csharp
public Colossal.Mono.Cecil.MetadataType MetadataType { get; }
```

- `public System.Boolean IsDefinition { get }`  

```csharp
public System.Boolean IsDefinition { get; }
```

- `public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set }`  

```csharp
public Colossal.Mono.Cecil.TypeDefinition DeclaringType { get; set; }
```

- `internal Colossal.Mono.Cecil.TypeDefinitionProjection WindowsRuntimeProjection { internal get; internal set }`  

```csharp
internal Colossal.Mono.Cecil.TypeDefinitionProjection WindowsRuntimeProjection { internal get; internal set; }
```


## Constructors

- `public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes)`  

```csharp
public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes);
```

- `public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes, Colossal.Mono.Cecil.TypeReference baseType)`  

```csharp
public TypeDefinition(System.String namespace, System.String name, Colossal.Mono.Cecil.TypeAttributes attributes, Colossal.Mono.Cecil.TypeReference baseType);
```


## Methods

- `protected virtual ClearFullName() : System.Void`  

```csharp
protected virtual System.Void ClearFullName();
```

- `public virtual Resolve() : Colossal.Mono.Cecil.TypeDefinition`  

```csharp
public virtual Colossal.Mono.Cecil.TypeDefinition Resolve();
```

- `private ResolveLayout() : System.Void`  

```csharp
private System.Void ResolveLayout();
```


## Nested types

- `Colossal.Mono.Cecil.TypeDefinition+<>c`  

