# Colossal.Mono.Cecil.DefaultReflectionImporter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.IReflectionImporter`  

## Code

```csharp
public class DefaultReflectionImporter : Colossal.Mono.Cecil.IReflectionImporter
{
    protected readonly Colossal.Mono.Cecil.ModuleDefinition module;
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Mono.Cecil.Metadata.ElementType> type_etype_mapping;

    public DefaultReflectionImporter(Colossal.Mono.Cecil.ModuleDefinition module);

    private static System.Boolean HasCallingConvention(System.Reflection.MethodBase method, System.Reflection.CallingConventions conventions);
    private static Colossal.Mono.Cecil.Metadata.ElementType ImportElementType(System.Type type);
    private Colossal.Mono.Cecil.FieldReference ImportField(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.ImportGenericContext context);
    private Colossal.Mono.Cecil.TypeReference ImportGenericInstance(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
    private static Colossal.Mono.Cecil.TypeReference ImportGenericParameter(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
    private static System.Void ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider provider, System.Type[] arguments);
    private Colossal.Mono.Cecil.MethodReference ImportMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
    private Colossal.Mono.Cecil.MethodReference ImportMethodSpecification(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context);
    private static System.Boolean ImportOpenGenericMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
    private static System.Boolean ImportOpenGenericType(System.Type type, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
    public virtual Colossal.Mono.Cecil.AssemblyNameReference ImportReference(System.Reflection.AssemblyName name);
    public virtual Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public virtual Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
    public virtual Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
    protected virtual Colossal.Mono.Cecil.IMetadataScope ImportScope(System.Type type);
    protected Colossal.Mono.Cecil.AssemblyNameReference ImportScope(System.Reflection.Assembly assembly);
    private Colossal.Mono.Cecil.TypeReference ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
    private Colossal.Mono.Cecil.TypeReference ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
    private Colossal.Mono.Cecil.TypeReference ImportTypeSpecification(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
    private static System.Boolean IsGenericInstance(System.Type type);
    private static System.Boolean IsMethodSpecification(System.Reflection.MethodBase method);
    private static System.Boolean IsNestedType(System.Type type);
    private static System.Boolean IsTypeSpecification(System.Type type);
    private static System.String NormalizeMethodName(System.Reflection.MethodBase method);
    private static System.String NormalizeTypeFullName(System.Type type);
    private static System.Reflection.FieldInfo ResolveFieldDefinition(System.Reflection.FieldInfo field);
    private static System.Reflection.MethodBase ResolveMethodDefinition(System.Reflection.MethodBase method);
    private System.Boolean TryGetAssemblyNameReference(System.Reflection.AssemblyName name, Colossal.Mono.Cecil.AssemblyNameReference& assembly_reference);
}
```


## Fields

- `protected readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
protected readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Mono.Cecil.Metadata.ElementType> type_etype_mapping`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.Mono.Cecil.Metadata.ElementType> type_etype_mapping;
```


## Constructors

- `public DefaultReflectionImporter(Colossal.Mono.Cecil.ModuleDefinition module)`  

```csharp
public DefaultReflectionImporter(Colossal.Mono.Cecil.ModuleDefinition module);
```


## Methods

- `private static HasCallingConvention(System.Reflection.MethodBase method, System.Reflection.CallingConventions conventions) : System.Boolean`  

```csharp
private static System.Boolean HasCallingConvention(System.Reflection.MethodBase method, System.Reflection.CallingConventions conventions);
```

- `private static ImportElementType(System.Type type) : Colossal.Mono.Cecil.Metadata.ElementType`  

```csharp
private static Colossal.Mono.Cecil.Metadata.ElementType ImportElementType(System.Type type);
```

- `private ImportField(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
private Colossal.Mono.Cecil.FieldReference ImportField(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private ImportGenericInstance(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference ImportGenericInstance(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private static ImportGenericParameter(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private static Colossal.Mono.Cecil.TypeReference ImportGenericParameter(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private static ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider provider, System.Type[] arguments) : System.Void`  

```csharp
private static System.Void ImportGenericParameters(Colossal.Mono.Cecil.IGenericParameterProvider provider, System.Type[] arguments);
```

- `private ImportMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : Colossal.Mono.Cecil.MethodReference`  

```csharp
private Colossal.Mono.Cecil.MethodReference ImportMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
```

- `private ImportMethodSpecification(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
private Colossal.Mono.Cecil.MethodReference ImportMethodSpecification(System.Reflection.MethodBase method, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private static ImportOpenGenericMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : System.Boolean`  

```csharp
private static System.Boolean ImportOpenGenericMethod(System.Reflection.MethodBase method, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
```

- `private static ImportOpenGenericType(System.Type type, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : System.Boolean`  

```csharp
private static System.Boolean ImportOpenGenericType(System.Type type, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
```

- `public virtual ImportReference(System.Reflection.AssemblyName name) : Colossal.Mono.Cecil.AssemblyNameReference`  

```csharp
public virtual Colossal.Mono.Cecil.AssemblyNameReference ImportReference(System.Reflection.AssemblyName name);
```

- `public virtual ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
public virtual Colossal.Mono.Cecil.TypeReference ImportReference(System.Type type, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public virtual ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.FieldReference`  

```csharp
public virtual Colossal.Mono.Cecil.FieldReference ImportReference(System.Reflection.FieldInfo field, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `public virtual ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context) : Colossal.Mono.Cecil.MethodReference`  

```csharp
public virtual Colossal.Mono.Cecil.MethodReference ImportReference(System.Reflection.MethodBase method, Colossal.Mono.Cecil.IGenericParameterProvider context);
```

- `protected virtual ImportScope(System.Type type) : Colossal.Mono.Cecil.IMetadataScope`  

```csharp
protected virtual Colossal.Mono.Cecil.IMetadataScope ImportScope(System.Type type);
```

- `protected ImportScope(System.Reflection.Assembly assembly) : Colossal.Mono.Cecil.AssemblyNameReference`  

```csharp
protected Colossal.Mono.Cecil.AssemblyNameReference ImportScope(System.Reflection.Assembly assembly);
```

- `private ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference ImportType(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context, Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind import_kind);
```

- `private ImportTypeSpecification(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context) : Colossal.Mono.Cecil.TypeReference`  

```csharp
private Colossal.Mono.Cecil.TypeReference ImportTypeSpecification(System.Type type, Colossal.Mono.Cecil.ImportGenericContext context);
```

- `private static IsGenericInstance(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean IsGenericInstance(System.Type type);
```

- `private static IsMethodSpecification(System.Reflection.MethodBase method) : System.Boolean`  

```csharp
private static System.Boolean IsMethodSpecification(System.Reflection.MethodBase method);
```

- `private static IsNestedType(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean IsNestedType(System.Type type);
```

- `private static IsTypeSpecification(System.Type type) : System.Boolean`  

```csharp
private static System.Boolean IsTypeSpecification(System.Type type);
```

- `private static NormalizeMethodName(System.Reflection.MethodBase method) : System.String`  

```csharp
private static System.String NormalizeMethodName(System.Reflection.MethodBase method);
```

- `private static NormalizeTypeFullName(System.Type type) : System.String`  

```csharp
private static System.String NormalizeTypeFullName(System.Type type);
```

- `private static ResolveFieldDefinition(System.Reflection.FieldInfo field) : System.Reflection.FieldInfo`  

```csharp
private static System.Reflection.FieldInfo ResolveFieldDefinition(System.Reflection.FieldInfo field);
```

- `private static ResolveMethodDefinition(System.Reflection.MethodBase method) : System.Reflection.MethodBase`  

```csharp
private static System.Reflection.MethodBase ResolveMethodDefinition(System.Reflection.MethodBase method);
```

- `private TryGetAssemblyNameReference(System.Reflection.AssemblyName name, Colossal.Mono.Cecil.AssemblyNameReference& assembly_reference) : System.Boolean`  

```csharp
private System.Boolean TryGetAssemblyNameReference(System.Reflection.AssemblyName name, Colossal.Mono.Cecil.AssemblyNameReference& assembly_reference);
```


## Nested types

- `Colossal.Mono.Cecil.DefaultReflectionImporter+ImportGenericKind`  

